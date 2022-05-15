# Climate Change in the USA over the last 100 years

### Project Idea
The project idea is to visualize minimum and maximum temperatures across the counties in the United States, along with the precipitation. Since the idea is to showcase climate change, the project will have the temperature and precipitation readings from different years.

### Significance and Broader Impacts
Understanding climate change and the patterns in temperature/precipitation changes can help us keep the ecosystem in a healthy condition. If we are ignorant towards climate change, it can cause natural disasters, human health issues and damage both man-made and natural systems.

This project should make it easier for people to visualize climate change and take appropriate action.

### Data Source
We will be using data from the National Centers for Environmental Information. The particular data that interested us is the temerature and perciptaion and will be obtain from [NCEI's data repository](https://www.ncei.noaa.gov/pub/data/cirs/climgrid/). 
In addition, the main shapefiles that we will be plotting on are available [here](https://www.ncei.noaa.gov/pub/data/cirs/climdiv/). The data will be of the past two years. And here is an example of one of the dataset included which is the Alaska’s average temperature in 2021 (2021.tave.alaska.pnt). It is organized by Latitude, Longitude and value from each Month. 

### Data Preprocessing
All the data preprocessing was done in `MS Excel`. This could be done in `Python` using its `Pandas` module but the required preprocessing was very simple so, `MS Excel` was sufficient.

Since the first column contains information about the year and county `FIPS` code, we needed to split up the digits into separate columns. `MS Excel` has a function `MID` which lets you extract a sub-string from a given string. Using that, the first column was split into `FIPS_CD` and `Years` column for all files. 
Then columns for the months were created by entering `January` for the third column header and letting `MS Excel` autofill the rest of the months.

The provided shape files contain the county `FIPS` code and the column is named `FIPS_CD`. This is why in the processed weather data files, the county `FIPS` code column was also named `FIPS_CD`. 

### Primary Functions
- Clickable counties on the map to get a more granular view
- Different color schemes to make it more accessible for color blind users
- Side by side comparisions of a given state and the entirity of the USA
- Timeline slider from `1895` to `2022` to let the user select a specific time period.

### Target Audience
The target audience for this project are the researchers trying to understand or visualize climate change in the USA over the last 100 years. Its also made for the other students in the course as it might be relevant to them as well.

### Multimedia
- An interactive map is definitely required where we can show temperatures and precipitations over a given time period

- A markdown or a text file which lists dataset sources, the process of making those maps and difficulties with working real data

### Project Format
For this project, our group wanted to include two pages that allow users to interact and explore the dataset. Both maps will use the Pseudo Mercator projection.

The first map is a generic interactive choropleth map:
 - It will have a time slider to see data from different years
 - Base map will be light monochrome
 - There will be total of 4 layers:
    - Maximum Temperature
    - Minimum Temperature
    - Average Temperature
    - Precipitation
- This will be centered at 39.8283° N, 98.5795° W

The second map will be more granular. It will let users compare specific states, years, months and type of data. The options for which state to compare will be present in a dropdown menu. Since it is a comparision map, it will be centered at the center of the given state. 