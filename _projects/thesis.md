---
layout: page
title: Who is the Public in our Public Libraries?
description: Senior Undergraduate Thesis
img: assets/img/cropped/library_crop.png
importance: 1
category: research
toc:
  sidebar: left
---

## Abstract 

Considering the privatization of space within urban landscapes and growing disparities in equity, libraries have incredible potential to shed light on community needs and the power of public space. This paper investigates the ways in which library services and uses vary across space and the ways in which they map onto the diverse socioeconomic & demographic characteristics of the neighborhoods that they serve. To answer this question, I map socio-demographic variables from the 2021 American Community Survey onto library service areas generated using Thiessen polygons and population weighted reaggregation. I surveyed the Chicago Public Library profiles to collect library service data which was then analyzed alongside the socio-demographic variables. The study revealed that library service areas display significant socio-economic and demographic variability that reflect Chicago’s racial and economic segregation. Additionally, socio-economic and demographic characteristics shape the services and programming available at local libraries. Affluent and predominantly white areas showed higher rates of circulation and availability of mental health services while neighborhoods that were predominantly poor, Black and/or Latinx Socio-economic and demographic characteristics significantly shape the services, programming, and amenities at Chicago libraries, with affluent and predominantly white areas receiving higher circulation and specialized services, while disadvantaged, predominantly Black and Latinx areas rely more on non-traditional services like internet access and social support. 

## Methods 

### Collect and Process Socio-Demographic Variables  

### Define Library Service Areas  

Libraries do not have formally defined geographic service areas and it was necessary to create spatial units for this analysis. The Chicago Data Portal maintains a data set of all Chicago Public Library Locations, contact information and usual hours of operation. The locations of the 81 libraries were plotted as points in GIS using their latitude and longitude coordinates from this data set. GIS was used to create proximal zones by generating Thiessen polygons from the library points.

```r
# Generate Thiessen/Voronoi polygons from library points

vorpoly <- st_union(points)%>%
  st_voronoi()%>%
  st_collection_extract("POLYGON")%>%
  st_sf %>%
  st_cast


# Because I had to union the points prior to st_voronoi() function the library attributes were lost
# Rejoin attributes from library points data to voronoi polygons 

vorjoin <- st_join(vorpoly, points)

# Clip Thiessen polygons by Chicago boundary 
chi_vor <- st_intersection(vorjoin, chi)%>%
  st_set_crs(st_crs("+proj=utm +zone=16 +datum=WGS84"))
  

```

### Population Weighted Reaggregation (PWR) 

The Thiessen Polygons representing LSAS, unfortunately, do not map neatly onto the Census geographies of blocks that contain the socioeconomic data. To address this, I apportion census data to service areas using a population weighted reaggregation technique. 

In order to increase the granularity of this data I transformed the sociodemographic data from one scale (tract) to another (block). I created a weighting factor that was the proportion of the census tract population in the individual block. This proportion was representative of the population contribution of an individual block towards the total population of the census tract that it belongs to. 

```r
# Calculate a  weighting factor that is the proportion of the census tract population in a every individual census block.This proportion is representative of the population contribution of an individual block towards the total population of the census tract that it belongs to.

weights_chi <- cook_blocks_tbl %>% 
  mutate(tract=substr(GEOID, 1, 11)) %>% 
  arrange(tract) %>% 
  merge(cook_tracts_tbl, by.x="tract", by.y="GEOID", all.x=T) %>% 
  mutate(block=substr(GEOID, 1, 16)) %>% 
  mutate(pop_wt=block_pop/tract_pop, hu_wt=block_hu/tract_hu)

```
 The proportion weight was then applied to the social demographic variables at the tract level so the result would be a weighted count by its population contribution.  

```r
# Apply the proportional weight to the social demographic variables 

acs_table_wt <- weights_chi %>% merge(acs_table, by.x="tract", by.y="GEOID", all.x=T) %>% mutate(latinx_app=pop_wt*latinx)%>%
mutate(for_app=pop_wt*for1)%>%
mutate(bach_app=pop_wt*et3)%>%
mutate(unemp_app=pop_wt*emp0)%>%
mutate(black_app=pop_wt*black)%>%
mutate(white_app=pop_wt*white)%>%
mutate(lang_app=pop_wt*noneng)%>%
mutate(asian_app=pop_wt*asian)%>% 
mutate(povtot_app=pop_wt*povtotal)%>%
mutate(child_app=pop_wt*child)%>%
mutate(yad_app=pop_wt*yad)%>%
mutate(mad_app=pop_wt*mad)%>%
mutate(sen_app=pop_wt*sen)%>%
mutate(man_app=pop_wt*male)%>%
mutate(fem_app= pop_wt*female)%>% 
mutate(hinc_app=pop_wt*highinc)

```

Apportioning the social demographic data to the LSAs consisted of generating centroids from the blocks and doing a centroid assignment to the LSAs. Sociodemographic data was aggregated by the name of the library service area and summed. Apportioning the data in this way allowed me to profile the sociodemographic characteristics and be confident in the quality of the data outputs. Apportioning the data in this way maintained an acceptable degree of data precision and accuracy. From this step I could normalize the data by the population in the LSA and further aggregate by whether a library provided a service or not.  

```r

# Generate centroids for the blocks
centroids <- st_centroid(chi_blocks_shp)

# Join library names to centroids
vor_blocks <- st_join(chi_vor, centroids, join= st_intersects, left=TRUE)

# Join weights table to library service data
lib_service <- acs_table_wt %>% 
  merge(vor_blocks, by.x="GEOID", by.y="GEOID.y", all.x=T)

#Aggregate variable apportionments

agg_latinx <- aggregate(latinx_app ~ NAME, data = lib_service, sum)
agg_unemp <- aggregate(unemp_app ~ NAME, data= lib_service, sum)
agg_college <- aggregate(bach_app ~ NAME, data= lib_service, sum)
agg_foreign <- aggregate(for_app ~ NAME, data=lib_service, sum)
agg_white<- aggregate(white_app ~ NAME, data=lib_service, sum)
agg_black<-aggregate(black_app ~ NAME, data=lib_service, sum)
agg_asian<-aggregate(asian_app ~ NAME, data=lib_service, sum)
agg_pov <- aggregate(povtot_app ~ NAME, data=lib_service, sum)
agg_child <- aggregate(child_app ~ NAME, data=lib_service, sum)
agg_yad <- aggregate(yad_app ~ NAME, data=lib_service, sum)
agg_mad <- aggregate(mad_app ~ NAME, data=lib_service, sum)
agg_sen <- aggregate(sen_app ~ NAME, data=lib_service, sum)
agg_man <- aggregate(man_app ~ NAME, data=lib_service, sum)
agg_fem <- aggregate(fem_app ~ NAME, data= lib_service, sum)
agg_noneng <- aggregate(lang_app ~ NAME, data= lib_service, sum)
agg_pop <- aggregate(block_pop ~ NAME, data= lib_service, sum)
agg_hinc <- aggregate(hinc_app ~ NAME, data=lib_service,sum)

# Join back to catchment layer
catchment <- chi_vor %>% merge(agg_latinx, by="NAME")%>% 
  merge(agg_unemp, by="NAME") %>% 
  merge(agg_college, by="NAME")%>% 
  merge(agg_foreign, by="NAME")%>% 
  merge(agg_white, by="NAME")%>%
  merge(agg_noneng, by= "NAME")%>%
  merge(agg_pop, by= "NAME")%>%
  merge(agg_black, by='NAME')%>%
  merge(agg_asian, by='NAME')%>% 
  merge(agg_pov, by='NAME')%>% 
  merge(agg_man, by= 'NAME')%>% 
  merge(agg_fem, by= 'NAME')%>% 
  merge(agg_child, by= 'NAME')%>% 
  merge(agg_yad, by= 'NAME')%>% 
  merge(agg_mad, by= 'NAME')%>% 
  merge(agg_sen, by= 'NAME')%>% 
  merge(agg_hinc, by='NAME')

```
```r

# Normalize

catchment.norm <-catchment %>% 

mutate(black_norm=black_app/block_pop, white_norm=white_app/block_pop, bach_norm=bach_app/block_pop, asian_norm=asian_app/block_pop, latinx_norm=latinx_app/block_pop, unemp_norm=unemp_app/block_pop, for_norm=for_app/block_pop, lang_norm=lang_app/block_pop, pov_norm=povtot_app/block_pop, child_norm=child_app/block_pop, yad_norm=yad_app/block_pop, mad_norm=mad_app/block_pop, sen_norm=sen_app/block_pop, man_norm=man_app/block_pop, fem_norm=fem_app/block_pop, hinc_norm=hinc_app/block_pop)

```

### Surveying Library Use, Services, and Programming  

## Results
