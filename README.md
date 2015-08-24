# Question

Our client needs an application that can calculate the sum of generation 
for all power stations in a collection of regions, over *n* points in time.

The application takes three json files as input:
- **station-metadata.json:** A collection of power station metadata including the id, name and GPS coordinates for each power station;
- **station-generation.json:** A collection of generation readings for each power station, for n points in time;
- **regions.json:** A collection of circular regions, defined by their radius and GPS coordinates.

All latitudes and longitudes are in decimal degrees, and all generation is in megawatts.

We need you to calculate which power stations fall geographically within each region, then sum their generation by region, for each point in time.

The output should be another json file with the following format (minus the comments):

~~~javascript
[
	{
		"TimeStamp": "2015-08-17T11:00:00+10:00",
		"Region": "Brisbane CBD",
		"SummedGeneration": 1000 // summed generation for each power station in the region "Brisbane CBD" for 11AM
	},
	{
        "TimeStamp": "2015-08-17T11:00:00+10:00",
        
		"Region": "South-West Queensland",
        "SummedGeneration": 1500 // summed generation for each power station in the region "South-West Queensland" for 11AM
        
	},
	...
	,
	{
		"TimeStamp": "2015-08-17T11:05:00+10:00",
		"Region": "Brisbane CBD",
		"SummedGeneration": 900 // summed generation for each power station in the region "Brisbane CBD" for 11:05AM
	},
	...
]
~~~

You can use the first formula from [this Wikipedia article](https://en.wikipedia.org/wiki/Great-circle_distance) to calculate distance from GPS coordinates (don't forget about converting from radians to degrees).

This is a product for our clients, so we need it to be robust and tested. Let us know any assumptions you make.

You are welcome to write the program in a language of your choosing, though we would prefer *C#* if possible. You can use any libraries you like - don't feel you have to write everything yourself.
