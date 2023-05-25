# GetSolarNoonTime
Getting Solar Noon times of the day, when you have the date and LatLong of the place
#Bird behaviour are almost always bimodal in their activity peaks in a day. Time data for behaviour can thus be converted based on Solar Noon, Solar Dusk or Solar Dawn times. 
#But procuring data for these times, across a large dataset of several spatial and temporal replicates can be difficult.
#Package suncalc to the rescue

dataforsun<- read.csv("~/Desktop/iiser/9th Semester/occupancy bird/collated bird data/finalirddata_compiled_for_ebird2.csv")
library(suncalc)
head(dataforsun)
head(dataforsun$date)
dataforsun$date<- as.Date(dataforsun$date) #converts date data into Date format
colnames(dataforsun)[c(5,22,23)]<- c("date", "lat", "lon") #The column names have to be changed to "dat', "lat", "lon"
getSunlightTimes( data=dataforsun[c(5,22,23)], tz="Asia/Kolkata") #Time zone is Asia/Kolkata. Default is the GMT time. 
