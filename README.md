# Question

Imagine our client needs an application that can calculate the total instantaneous power station generation in a number of geographical regions, at various times of the day.

The application takes three files as input:

-   **station-metadata.json:** power station metadata including the id, name and GPS coordinates of each power station;
-   **station-generation.json:** instantaneous generation readings for each power station, for multiple points in time;
-   **regions.json:** A collection of circular geographical regions, defined by their radius (inclusive) and the GPS coordinates at their centre.

All latitudes and longitudes are in decimal degrees, and all generation is in megawatts (MW).

We need you to calculate which power stations fall geographically within each region, then sum their instantaneous generation by region, for each point in time.

The output should be another json file with the following format (minus the comments):

```javascript
// This is just example data...
[
	{
		"TimeStamp": "2015-08-17T11:00:00+10:00",
		"Region": "QLD",
		"SummedGeneration": 1000 // Summed generation (in MW) for power stations in the region "QLD" for 11AM
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
```

The first formula from [this Wikipedia article](https://en.wikipedia.org/wiki/Great-circle_distance) can be used to calculate the distance between GPS coordinates (don't forget about converting from decimal degrees to radians).

# Other Considerations

-   The first thing we'll want to do (before we even look at your code) is to **demonstrate your running solution** so please make that easy for us; that can be anything from a simple command line to run to point us to an already deployed app
-   We don't want this to take you too long, so keep the solution (especially the UI) simple. Our focus will be on the quality of the code, not the quantity
-   You are welcome to write in any language of your choosing. If you need help making a choice we're mostly familiar with **`C#`**, **`JavaScript`** or **`TypeScript`**
-   You can use 3rd party libraries if you like - don't feel you have to write everything yourself
-   Please don't make the source code of your final solution public (use dropbox, email, private github etc.)
-   If you think it's appropriate, include a README with your code to describe any decisions you made along the way
-   What we're want to know is _how_ you go about your solution. For example, is your code readable, robust and extensible? We will be keen to to discuss your solution with you
