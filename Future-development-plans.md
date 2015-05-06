Items I'd like to address in future versions:

1. Support for more of Highcharts' chart types
	- Many of them are silly but there's a few that could be truly useful
		- http://www.highcharts.com/demo
			- Stacked Bar/Column *
			- Column Range
			- Scatter *
			- Bubble *
			- Tree Map

			Items with a * are either very easy or particularly valuable
2. Support for Highstock and Highmaps
	- Much of the abstraction needed to make this support workable has already been done so this shouldn't require major refactoring
		- http://www.highcharts.com/stock/demo
		- http://www.highcharts.com/maps/demo
			- This one especially will require some implementation/UI thought as it'll likely need very different treatment than Highcharts and Highstock
3. Use iframes to embed the JS version of chart inside of a post
	- Admin ajax URLs perhaps?
4. External embeds
	- Allow charts to be embedded on external sites if the site owner wishes to allow this
	- The iframe stuff is related to this and likely necessary in order to support this
5. Responsive charts (where the height AND width are responsive instead of just the width)
	- The responsive width charts are actually pretty good and may still be the best solution, given how compressing line charts can make them unreadable. This is still at least worth looking into.