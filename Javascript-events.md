There are two Javascript events that occur when a Highcharts chart is rendering.  One occurs immediately before the chart renders and one immediately after.  These are carried out using the jQuery custom events functionality.

### `render_start` ###

Render start occurs immediately before a Highcharts chart starts rendering.  

The event has the chart's WordPress post ID value available to it, which in turn would allow you to manipulate the `m_chart_highcharts_ID` object.

Example:

```js
$( '.m-chart' ).on( 'render_done', function(){
});
````

### `render_done` ###