---
layout: page
title: Who is the Public in our Public Libraries?
description: Exploring the Spatial Variations of Library Services in Chicago, IL. 
img: assets/img/thumbnails/thesis_crop.png
importance: 1
category: research
pretty_table: true
citation: true
toc:
  sidebar: left
---

## Abstract 

Considering the privatization of space within urban landscapes and growing disparities in equity, libraries have incredible potential to shed light on community needs and the power of public space. This paper not only investigates the ways in which library services/uses vary across space but also the ways in which they map onto the diverse socioeconomic and demographic characteristics of the neighborhoods that they serve. In this study, I map socio-demographic variables from the 2021 American Community Survey onto library service areas generated using Thiessen polygons. I surveyed Chicago Public Library web profiles to collect library service data, which was then analyzed alongside the socio-demographic variables. The results of this research reveal a relationship between socio-demographic variables and library services among library service areas, with noticeable variability across the city — which is reflective of Chicago's longstanding history of racial and economic segregation. Socio-economic and demographic characteristics significantly relate to the services, programming, and amenities found in Chicago libraries. Rather than using libraries in their "traditional" book lending sense, disadvantaged areas seem to rely more on non-traditional services that libraries offer, like internet access and social supports. Considering challenges that these neighborhoods might face, like lower incomes and educational attainment, and limited access to the internet, these patterns may be due to targeted efforts of local libraries to meet the needs of their constituents. However, this study also reveals gaps in access, specifically related to libraries that do not offer mental health and citizenship support services but are situated in communities that would benefit from them.
<br>

## Methods 

### Collect and Process Socio-Demographic Variables  
The social and demographic variables (see Table 1) used in this study were obtained from the 2021 American Community Survey (ACS) 5-year estimates and 2020 decennial United States Census. Socio-demographic variables from the ACS were obtained at the Census tract level. Population counts were obtained both at the tract and block level from the US Census. 

*Table 1: Neighborhood characteristic variables considered in this study* 

| Category | Census variables |
| :----------- | :------------: | 
| Economic        | Median family income, Employment status, Poverty Status|
| Demographic     | Total population, Race, Ethnicity, Age, Sex  |
| Social/Cultural | Nativity, Educational attainment  |

<br>

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

<div class="row justify-content-sm-center">
  <div class="col-10 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/thesis/chi_voronoi.png" title="Library Service Areas" class="img-fluid rounded z-depth-1" zoomable=true %}
  </div>
</div>
<div class="caption">
    Library branches and service areas in Chicago, IL   
</div>
<br>

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

Apportioning the social demographic data to the LSAs consisted of generating centroids from the blocks and doing a centroid assignment to the LSAs. Sociodemographic data was aggregated by the name of the library service area and summed. Apportioning the data in this way allowed me to profile the sociodemographic characteristics and be confident in the quality of the data outputs. Apportioning the data in this way maintained an acceptable degree of data precision and accuracy. From this step I could normalize the data by the population in the LSA and further aggregate by whether a library provided a service or not.  
<br>

### Surveying Library Use, Services, and Programming  

Libraries’ increased web presence has afforded us the possibility to explore the kinds of services they offer other than print material circulation. The Chicago Public Library has a library profile for its 81 neighborhood branches on their official website (www.chipublib.org). An initial scan of 3 library profiles revealed that the profiles were conveniently formatted to be more or less identical to each other. This initial scan also allowed me to create a list of variables (Table 2) for my survey that I planned to look out for and include in my study. Data on the non-traditional programming and features (see Table 2) was then collected over a period of two days by visiting each library profile with an eye for the variables in my list. The presence of said features was manually coded as a Boolean feature into an Excel spreadsheet. 

*Table 2. Library features as listed on the CPL website* 

| Library “Feature”     | Feature Definition & Notes   |
| :---------------: | :-------------: |
| Citizenship Corner | Enhanced collections on immigration and U.S citizenship, free assistance, and dissemination of USCIS publications in commonly spoken languages | 
| Cyber Navigators | One-on-one sessions with technology tutors that build computer literacy and digital skills |
| YouMedia | Teenager digital learning and makerspace  |
| Teacher in the Library | Free drop-in homework help program for school-age students with accredited teachers |
| Mental Health and Social Services | Staffed with mental health clinicians or hosts a mental health focused organization |
| Wi-Fi Hotspot Lending  | A program that lends portable wifi hotspots that you can use to connect a mobile-enabled device to the internet |  
| Chromebook Kit Lending  | A resident of Chicago with an active adult CPL card may borrow a Google Chrome laptop for three weeks |
| Non-English Language Materials |The library provides a multilingual materials collection and circulates materials in a language other than English |

<br>

## Results

*Table 3. Summary table of descriptive statistics for demographic variables*

| Category                  | Median  | SD     | Min   | Max    |
|:-------------------------:|:-------:|:------:|:-----:|:------:| 
| **Demographic Variables** |         |        |       |        |
| Total Population          | 33,134  | 13,906 | 7,892 | 68,729 |
| Child                     | 5,333   | 2,489  | 1,500 | 14,002 |
| Senior                    | 8,194   | 3,322  | 1,254 | 18,431 |
| Female                    | 16,468  | 6,833  | 4,042 | 35,930 |
| **Racial & Ethnic Variables** |      |        |       |        |
| Black                     | 5,856   | 10,370 | 70    | 41,499 |
| Asian                     | 1,113   | 2,957  | 0     | 12,114 |
| Latinx                    | 5,702   | 10,691 | 225   | 49,158 |
| White                     | 5,830   | 12,162 | 26    | 51,128 |
| **Economic Variables**    |         |        |       |        |
| Unemployed                | 8,759   | 3,529  | 2,360 | 21,640 |
| Poverty Status            | 5,411   | 3,086  | 977   | 13,907 |
| High Income               | 1,371   | 3,073  | 79    | 14,467 |
| **Social Variables**      |         |        |       |        |
| Foreign Born              | 5,299   | 5,693  | 57    | 25,840 |
| Attained Degree           | 4,801   | 5,475  | 445   | 26,028 |

<br>

<iframe src="assets/html/race_interactive2.html" height="600px" width="100%" style="border:none;"></iframe>




