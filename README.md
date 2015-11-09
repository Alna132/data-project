# data-project
## Data Representation and Querying Project 2015
### Student Name

## Introduction
This project provides the design and documentation for the dataset "Dataset title" which is available at [data.gov.ie](http://data.gov.ie)...

## About the data
This dataset was received in Comma Separated Values (CSV) format, and was downloaded from [Galway City Car Parking](https://data.gov.ie/dataset/galway-city-car-parking-locations/resource/d967950d-faab-45ad-815d-211c9bcfb38e).
The CSV file contains 18 rows, the first being a header row with the names of each field.
There are twelve values on each line, which are as follows:

    - **x**: the year that the car was purchased.
    - **y**: the price of the car.
    - **ObjectId**: 
    - **Name**: 
    - **Type**: 
    - **No_Spaces**: 
    - **Lat**: 
    - **Long**: 
    - **EastITM**: 
    - **NorthITM**: 
    - **EastIG**: 
    - **NorthIG**: 

## List of cars for a given year
You can get a list of cars purchased in a given year using the GET method at the following URL:

*http://carsapi.com/year/[year]*
where you replace [year] with the year.
For example, the URL:

*http://carsapi.com/year/2005*
will return a list of cars purchased in 2005.

The data will be returned in JSON format, with the following properties for each car:

    - *price*: the price of the car.
    - *model*: the model of the car.
    ...

An example of a response would be:

    ```json
    [ {"price": 20000, "model": "Skoda", ...}, {...}, ...]
    ```

