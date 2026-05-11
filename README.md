# Surface Heat in Motion

### Our Starting Process

  After reviewing the GOES, CMIP6, and NASA MODIS datasets, we were initially intrigued by exploring cloud motion and formation surrounding storms contained in the GOES data. However, upon further exploration of NASA MODIS, we decided to pivot to the global daily satellite imagery collected by NASA’s Terra satellite.

### Motivation

  Our motivation for this pivot was seeing, through EDA, how land surface temperature is both spatial and temporal. We observed how heat patterns are not evenly distributed across the Earth’s hemispheres, and how this distribution changes throughout the year with seasonal shifts. While a static map could show momentary snapshots of the land surface temperature, an interactive plot using the NASA MODIS Terra satellite imagery from NASA GIBS would be able to show how patterns change over time and show corresponding changes in heat intensity across different latitude bands. Therefore, our project explores the question: how does land surface heat shift across latitude and season in 2025? The goal of our visualization is to help viewers explore global surface heat patterns by connecting the three dimensions: location, time, and latitude.

### Dataset

  Our project uses NASA’s MODIS Terra satellite imagery from 2025 to show global surface temperature patterns. For this project, we used monthly samples from 2025, selecting one representative date from each month. While the map displays NASA’s official images directly, our charts are built by sampling the colors of the pixels in those images. We then convert those colors into a relative heat index, which allows us to calculate and graph heat trends based on the visual data.

### EDA Process

  Through exploratory data analysis of the measurements contained in this data, such as land temperature and vegetation, we created visualizations that gave insight into how the heat index was distributed in 2025.

Our visualizations can be viewed here: https://hannahhuangh.github.io/Surface_Heat_In_Motion/exploratory.html

  We researched different aspects of surface heat including monthly surface heat index, latitude heat gradient, seasonal comparison, heat intensity distribution, and comparing the northern vs. southern hemispheres. These metrics allowed us to identify the relationship between solar energy and Earth’s geography and identify trends, such as the "plateau effect" near the tropics and the bimodal distribution of global heat, which dictated the functional requirements of our interactive dashboard. Our main focus was to explore the relative heat index spatially across the world. The relative heat index is a 0–100 score that is calculated from the MODIS image pixels. Warmer colors represent higher temperatures, while cooler colors represent lower temperatures. Since the index is based on the color of the image, it cannot be interpreted as exact Celsius temperatures. Instead, it is used as a comparative scale that gives us an estimate of temperatures over time and location around the world.

  This data transformation was important because it allowed us to turn satellite images into meaningful conclusions. By aggregating the relative heat index by month and latitude band, we are able to make comparisons across seasons and based on location.

### Design Rationale

  The color scale, from dark blue to red, was intentionally chosen to match the human intuition that areas with colder surface land temperature are blue and warmer temperatures are red. This color choice also ensures that the visualizations are easy to interpret quickly because the encoding matches a familiar temperature scale rather than forcing viewers to adjust to an unfamiliar color system. Additionally, we designed the visualization to be a map of the entire globe. This allows for geographical comparisons and insights about how land surface temperatures vary due to factors such as proximity to the equator or water. As the land surface temperature is spatial, a world map is the best primary encoding for showing how regions differ in temperature.
  
  For our initial interaction, we made a time slider to show monthly change in land surface temperature. We developed this to be more insightful for the viewer by linking charts that depict corresponding changes in the heat index and latitude heat profile. This makes the interaction more meaningful than just switching satellite pictures because the viewer can connect the pattern on the map to numerical summaries. Additionally, selecting points on the latitude heat profile chart highlights an orange latitude band, which facilitates comparisons over time for a specific part of the Earth. The selected latitude band also connects the map and chart views, allowing the viewer to track how the band changes across the months of 2025 instead of just exploring global averages. Further, we added a hover tooltip over the map that gives information about the date as well as latitude and longitude coordinates without cluttering the visualization.

With the addition of our extra latitude band over time graphs, we are given the ability to answer the following questions: 
  1) How does heat change over time near the equator?
  2) How does a northern latitude compare to a southern latitude?
  3) Which months are warmest for a selected latitude band?


### Development Process

  We began by creating exploratory visualizations to understand which patterns were most important in the MODIS imagery. Our exploratory analysis included monthly heat summaries, latitude gradients, seasonal comparisons, heat intensity distributions, hemisphere comparisons, and raw MODIS image snapshots. These plots showed that time and latitude/location were strong dimensions.

  After the EDA stage, we built the main visualization using D3.js. We first implemented the NASA GIBS map layer and the monthly time slider and added zooming, panning, and hover tooltips for geographic exploration. Next, we created the linked charts by sampling MODIS image pixels and aggregating the relative heat index values.

  The most challenging part was turning rendered satellite imagery into charted values. Since the GIBS layer is an image rather than a raw Celsius dataset, we had to create and clearly explain the relative heat index. Another major challenge was linking all interactions together so that the slider, map, monthly chart, latitude chart, and selected-latitude trend chart update consistently.

## Conclusion

  Our final visualization allows viewers to explore how land surface heat shifts across Earth in 2025. Our project combines real NASA MODIS imagery with interactive linked charts that users can use to investigate both spatial and temporal patterns. By connecting the time slider, map, latitude profile, and selected latitude trend chart, the visualization supports a richer exploration of how surface heat varies by location and time. Therefore, it allows viewers to extract insights beyond what a static map could provide by allowing multi-dimensional comparisons of surface heat across both space and time.

Our final interactive visualization can be viewed here: https://hannahhuangh.github.io/Surface_Heat_In_Motion/


