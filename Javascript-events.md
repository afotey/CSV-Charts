There are two Javascript events that occur when a Highcharts chart is rendering.  One occurs immediately before the chart renders and one immediately after.  These are carried out using the jQuery custom events functionality.

### `render_start` ###

`render_start` occurs immediately before a Highcharts chart starts rendering.  

The event has the chart's WordPress post ID value available to it, which in turn would allow you to manipulate the `m_chart_highcharts_ID` object or the container divs that the chart will render inside of.

Example:

```js
$( '.m-chart' ).on( 'render_start', function( event ){
	$( '.m-chart-container-' + event.post_id ).addClass( 'awesome-chart' );
});
````

### `render_done` ###

`render_done` occurs immediately after a Highcharts chart has finished rendering.  

The event has the chart's WordPress post ID value available to it and more importantly the Highcharts chart object.  

The M Chart admin panel Javascript uses this event to generate the high resolution PNG version of the graph.  However, it could be used to manipulate the chart object however you wished.

See the [Highcharts API](http://api.highcharts.com/highcharts) reference Methods and Properties section for all the possibilities.

Example:

```js
$( '.m-chart' ).on( 'render_done', function( event ){
	event.chart.addSeries({
		data: [194.1, 95.6, 54.4, 29.9, 71.5, 106.4]
	});
});
````