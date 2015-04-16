## Types of charts ##
M Chart currently supports 6 types of chart:

1. [Line](https://github.com/methnen/m-chart/wiki/Chart-Examples#line)
2. [Spline](https://github.com/methnen/m-chart/wiki/Chart-Examples#spline)
3. [Area](https://github.com/methnen/m-chart/wiki/Chart-Examples#area)
4. [Column](https://github.com/methnen/m-chart/wiki/Chart-Examples#column)
5. [Bar](https://github.com/methnen/m-chart/wiki/Chart-Examples#bar)
6. [Pie](https://github.com/methnen/m-chart/wiki/Chart-Examples#pie)

## Creating a chart ##

Here's a screenshot of the M Chart UI:

![M Chart UI](https://methnen.com/misc/m-chart/ui.png)

You'll see a spreadsheet interface at the top.  This is where you'll input your data.  It works similarly to Google Spreadsheet or Excel.

In the screenshot you'll see that the user has put two columns of sales data (iPad and iPhone) broken up by Quarter.

They could have also put to rows of sales data and simply flipped the **Parse in** setting to **Rows** instead of columns.  Also note that the first two quarters there was no reported iPad sales data.  It's fine to leave values like that blank.  M Chart will set them as a null values in Highcharts and everything will still render fine.

Lets look at a more simple chart:

![Spline Chart](https://methnen.com/misc/m-chart/spline.png)

This one only has one set of Revenue data.  So the spreadsheet for this one is a bit simpler:

![Spline Data](https://methnen.com/misc/m-chart/spline-data.png)

You'll see in this case they entered data in a row versus in a column.  That's reflected in the settings panel for this chart:

![Spline Settings](https://methnen.com/misc/m-chart/spline-settings.png)

Line, Spline, Area, Column, and Bar charts all have roughly the same options available in the settings panel.  One exception is the **Force vertical axis minimum to zero** option which is only available on Line and Spline charts.

Highcharts tries to always give a little padding above and below the minimum values in a chart.  Most of the time this is a good thing but it's occasionally troublesome. 

Let's pretend that Apple's Q1 2010 sales were only 1 Billion (I know hard to imagine):

![Y Axis Min Issue](https://methnen.com/misc/m-chart/y-axis-min-problem-example.png)

Highcharts pads the bottom of the graph and you end up with negative values in the Y Axis.  This is ugly in this situation because we all know Apple could never have negative sales.  If you check the **Force vertical axis minimum to zero** option you end up with a chart that looks like this:

![Fixed Y Axis Minimum](https://methnen.com/misc/m-chart/y-axis-min-fixed-example.png)

Pie charts are simpler since they can only ever have one set of data in them.  Here's an example pie chart illustrating pickle popularity by type (according to my wild guess):

![Pie Chart](https://methnen.com/misc/m-chart/pie.png)

The spreadsheet for this data set is quite simple:

![Pie Data](https://methnen.com/misc/m-chart/pie-data.png)

Pie charts also have simplified chart options:

![Pie Settings](https://methnen.com/misc/m-chart/pie-settings.png)

## Embedding charts in your posts ##

Once you've got a chart you want to use in a post make sure you've published it.  Then copy the Shortcode generated for you at the bottom of the chart settings (clicking on the field will automatically select the entire shortcode for you):

![Pie Settings](https://methnen.com/misc/m-chart/pie-settings.png)

You'll notice an Image field and View button to the right of the Shortcode field. Every time you update your chart post a high resolution PNG copy will be generated as well.

The shortcode is smart enough that it will use the image version in situations where the Javascript version will not work. The best example of that is in your RSS or Atom feeds.