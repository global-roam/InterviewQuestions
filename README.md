# Question

Imagine our client needs an application that can calculate the total instantaneous power station generation in a collection of geographical regions, at *n* points in time.

The application takes three json files as input:
- **station-metadata.json:** A collection of power station metadata including
  the id, name and GPS coordinates of each power station;
- **station-generation.json:** A collection of instantaneous generation readings for each
  power station, for *n* points in time;
- **regions.json:** A collection of circular geographical regions, defined by their radius
  (inclusive) and the GPS coordinates at their centre.

All latitudes and longitudes are in decimal degrees, and all generation is in
megawatts (MW).

We need you to calculate which power stations fall geographically within each
region, then sum their instantaneous generation by region, for each point in time.

The output should be another json file with the following format (minus the
comments):

~~~javascript
// This is just example data...
[
	{
		"TimeStamp": "2015-08-17T11:00:00+10:00",
		"Region": "QLD",
		"SummedGeneration": 1000 // Summed generation (in MW) for each power station in the region "QLD" for 11AM
	},
	{
		"TimeStamp": "2015-08-17T11:00:00+10:00",
		"Region": "NSW",
		"SummedGeneration": 1500 // Summed generation for "NSW" for 11AM
	},
	...
	{
		"TimeStamp": "2015-08-17T11:05:00+10:00",
		"Region": "QLD",
		"SummedGeneration": 900 // Summed generation for "QLD" for 11:05AM
	},
	...
]
~~~

You can use the first formula from [this Wikipedia article](https://en.wikipedia.org/wiki/Great-circle_distance)
to calculate the distance between GPS coordinates (don't forget about converting
from decimal degrees to radians).

Imagine this is a product for our clients, so we need it to be robust and tested.
Let us know any assumptions you make. We don't want this to take too long, so a simple console app is sufficient. Our focus will be on the quality of the code, not the quantity.

You are welcome to write the program in a language of your choosing, though we
would prefer **C#** if possible. You can use any libraries you like - don't feel
you have to write everything yourself.

Please make the source code of your final solution available to us via dropbox,
email, private github or some other method (we just ask that you don't make the
solution public). What we're really interested in is *how* you solve the problem.
For example, is your code readable, robust and extensible? We will be keen to
discuss your solution with you.
