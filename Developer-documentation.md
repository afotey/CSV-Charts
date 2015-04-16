M Chart has a number of filter/action hooks as well as some Javascript events that you can use to integrate M Chart into your website.

## Action Hooks ##

### `m_chart_update_post_meta` ###

This is an action that is triggered whenever someone updates a chart's post meta.

The meta array has already been cleaned and validated at the time the action is triggered.

- Arguments
	- `$post_id`
		- The WP ID of the chart post
	- `$parsed_meta`
		- The cleaned and parsed meta array for the chart

### `m_chart_post_render_javascript` ###

This is an action that is triggered when generating the Javascript and HTML used to render a chart.

Potentially this could be used to include some Javascript code that would run after a chart has finished rendering.  This is great spot to add a watermark via an SVG file.

The Javscript should have the Highcharts `chart` object available to it and can also access to the chart args for the current chart since you know the ID of the post.

- Arguments
	- `$post_id`
		- The WP ID of the chart post
	- `$args`
		- The arguments that were passed to the `get_chart` method

Example:

```php
function m_chart_post_render_javascript( $post_id, $args ) {
	?>
	chart.renderer.image('http://domain.com/img/logo.svg', 11, 10, 106, 16).add();
	<?php
}

add_action( 'm_chart_post_render_javascript', 'action_m_chart_post_render_javascript', 10, 2 );

````

## Filter Hooks ##

### `m_chart_chart_args` ###

This filter hook is triggered after all of the Highcharts chart args for a given chart have been generated.

This hook is useful for changing the behavior of the plugin in regards to how it displays/functions.

You could reformat the tooltips for instance, or you could modify axis title text.  You could also add arguments to the chart args that M Chart doesn't use by default like change the colors used to render the chart.

See the [Highcharts API](http://api.highcharts.com/highcharts) reference for all the posibilities.

- Arguments
	- `$chart_args`
		- The Highcharts chart args for the chart
	- `$post`
		- The WP post object for the chart
	- `$post_meta`
		- The WP `post_meta` for the chart
	- `$args`
		- The args passed to the `get_chart` method

Example:

```php
function m_chart_chart_args( $chart_args ) {
	$chart_args['colors'] = array(
		'#2f7ed8',
		'#0d233a',
		'#8bbc21',
		'#910000',
		'#1aadce',
		'#492970',
		'#f28f43',
		'#77a1e5',
		'#c42525',
		'#a6c96a',
	);

	return $chart_args;
}

add_filter( 'm_chart_chart_args', 'filter_m_chart_chart_args', 10 );

````

### `m_chart_chart_options` ###

This filter hook is triggered after all of the Highcharts chart options have been generated.

Chart options are library wide settings that you may want to change or override.  M Chart uses them to set some USA standard formatting and numeric abbreviations.

This hook is useful for changing the behavior of Highcharts.

Most of the options involve localization stuff.  For instance you could change the decimal indicator to a comma which is used in some European contries.

See the [Highcharts API](http://api.highcharts.com/highcharts) reference for all the posibilities.

- Arguments
	- `$chart_options`
		- The Highcharts options
	- `$library`
		- The active library (currently will also be 'highcharts')

Example:

```php
function m_chart_chart_args( $chart_options ) {
	$chart_options['lang']['decimalPoint'] = ',';

	return $chart_options;
}

add_filter( 'm_chart_chart_args', 'filter_m_chart_chart_args', 10 );

````