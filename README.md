## Data Representation and Querying Project 2015
### Alanna Curran

## Introduction
This project provides the design and documentation for the dataset "Galway City Car Parking" which is available at [data.gov.ie](http://data.gov.ie).
I chose the Galway city car parking dataset as when people drive into galway its handy to know where the car parks are, whether you have to pay to use it and how many spaces it has. 

## About the data
This dataset was received in Comma Separated Values (CSV) format, and was downloaded from [Galway City Car Parking](https://data.gov.ie/dataset/galway-city-car-parking-locations/resource/d967950d-faab-45ad-815d-211c9bcfb38e).
The CSV file contains 18 rows, the first being a header row with the names of each field.
There are twelve values on each line, which are as follows:

- **x**: The X-coordinate of the Caspar.
- **y**: The Y-coordinate of the car park.
- **ObjectId**: An identifiatn number for each car park.
- **Name**: The name of the car park.
- **Type**: The type of car park (ie. Multi-storey, surface car park, paying, etc.).
- **No_Spaces**: The capacity of the car park.
- **Lat**: The latitude of the car park.
- **Long**: The longitude of the car park.
- **EastITM**: The easting coordinate of the Irish transverse Mercator, it means that the location is x metres east from the false origin (along the X-axis).
- **NorthITM**: The northing coordinate of the Irish transverse Mercator, it means that the location is x metres north from the false origin (along the Y-axis).
- **EastIG**: The easterly Irish Grid reference number relative to the origin of the entire grid.
- **NorthIG**: The northerly Irish Grid reference number relative to the origin of the entire grid.

### Reference:
EastITM & NorthITM: 
> An ITM co-ordinate is generally given as a pair of two six-digit numbers (excluding any digits behind a decimal point which may be used in very precise surveying). The first number is always the easting and the second is the northing. The easting and northing are in meters from the false origin.
> [Wikipedia](https://en.m.wikipedia.org/wiki/Irish_Transverse_Mercator)

EastIG & NorthIG:
> Coordinates may also be given relative to the origin of the entire 500 by 500 km (310 by 310 mi) grid (in the format easting, northing). 
> [Wikipedia](https://en.m.wikipedia.org/wiki/Irish_grid_reference_system#Eastings_and_northings)

## List of car parks by type
You can get a list of car parks of a certain type by using the GET method at the following URL:

*http://parking-galway.ie/type/[type]*
where you replace [type] with the type of car park you're looking for.
For example, the URL:

*http://parking-galway.ie/type/surface*
will return a list of car parks that are surface car parks.

The data will be returned in JSON format, with the following properties for each car:

- *Name*: The name of the car park.
- *Type*: The type of car park.
- *No_Spaces*: The number of spaces in the car park.
- *Lat*: The latitude of the car park.
- *Long*: The longitude of the car park.

An example of a response would be:

```json
[ {"Name": "Market St", "Type": "Pay/Surface Carpark", "No_Spaces": 88, "Latitude": 53.273, "Longitute": -9.054},
  {"Name": "Gaol Rd/Cathedral", "Type": "Pay/Surface Carpark", "No_Spaces": 161, "Latitude": 53.274, "Longitute": -9.057},
  {"Name": "Harbour", "Type": "Pay/Surface Carpark", "No_Spaces": "N/A", "Latitude": 53.27, "Longitute": -9.052},
  {"Etc..."}
]
```

## List of all car parks.

You can get a list of all the car parks by using the GET method at the following URL:
*http://www.parking-galway.ie/all*
This will return a list of cars purchased in 2005.

The data will be returned in JSON format, with the following properties for each car:
- *Name*: The name of the car park.
- *Type*: The type of car park.
- *No_Spaces*: The number of spaces in the car park.
- *Lat*: The latitude of the car park.
- *Long*: The longitude of the car park.
- *EastITM*: The east Irish Transvers Mercator coordinate.
- *NorthITM*: The north Irish Transverse Mercator coordinate.
- *EastIG*: The east Irish Grid coordinate.
- *NorthIG*: The north Irish Grid coordinate.


An example of a response would be:
```json
[ {"Name": "Market St", "Type": "Pay/Surface Carpark", "No_Spaces": 88, "Latitude": 53.273, "Longitute": -9.054, "EastITM": 529691.955, "NorthITM": 725294.803, "EastIG": 129726.012, "NorthIG": 225265.639},
  {"Name": "Jurys Hotel", "Type": "Multistorey Carpark", "No_Spaces": 348, "Latitude": 53.271, "Longitute": -9.055, "EastITM": 529691.955, "NorthITM": 725294.803, "EastIG": 129726.012, "NorthIG": 225265.639},
  {"Name": "Gaol Rd/Cathedral", "Type": "Pay/Surface Carpark", "No_Spaces": 161, "Latitude": 53.274, "Longitute": -9.057, "EastITM": 529691.955, "NorthITM": 725294.803, "EastIG": 129726.012, "NorthIG": 225265.639},
  {"Name": "Harbour", "Type": "Pay/Surface Carpark", "No_Spaces": "N/A", "Latitude": 53.27, "Longitute": -9.052, "EastITM": 529691.955, "NorthITM": 725294.803, "EastIG": 129726.012, "NorthIG": 225265.639},
  {"Etc..."}
]
```
