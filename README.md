# data-project
## Data Representation and Querying Project 2015
### Student Name

## Introduction
This project provides the design and documentation for the dataset "Dataset title" which is available at [data.gov.ie](http://data.gov.ie)...

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
- **EastIG**: 
- **NorthIG**: 

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
  {"Name": "Jurys Hotel", "Type": "Multistorey Carpark", "No_Spaces": 348, "Latitude": 53.271, "Longitute": -9.055},
  {"Name": "Gaol Rd/Cathedral", "Type": "Pay/Surface Carpark", "No_Spaces": 161, "Latitude": 53.274, "Longitute": -9.057},
  {"Name": "Harbour", "Type": "Pay/Surface Carpark", "No_Spaces": "N/A", "Latitude": 53.27, "Longitute": -9.052},
   {"Etc..."}
]
```
