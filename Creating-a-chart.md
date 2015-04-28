Here's a screenshot of the M Chart UI:

![M Chart UI](https://methnen.com/misc/m-chart/ui.png)

You'll see a spreadsheet interface at the top.  This is where you'll input your data.  It works similarly to Google Spreadsheet or Excel.

In the screenshot you'll see that the user has put two columns of sales data (iPad and iPhone) broken up by Quarter.

They could have also put two rows of sales data and simply flipped the **Parse in** setting to **Rows** instead of columns.  Also note that the first two quarters there was no reported iPad sales data.  It's fine to leave values like that blank.  M Chart will set them as a null value in Highcharts and everything will still render fine.

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