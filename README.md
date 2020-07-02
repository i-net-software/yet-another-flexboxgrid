# This is yet another flexboxgrid

It has been inspired by a slew other projects to kind of normalize the naming conventions for a flexbox grid. The focus is the LESS file to use it in other projects.

What it does differently is the mostly generative way to create the column specs. Also: it allows to create an arbitrary number of columns (but you should stick to 12 I think).

Another thing it does differently is the handling of screen sizes. You can - of course - set up boundaries for the required media sizes; but it also defines specific queries for mobile and tablet devices.

The default - and customizable - values are:

	@grid-columns: 12;       		// Number of columns to generate
	@grid-gutter: .5rem;			// the base value for space between the cells
	@query-xs-max-width: 786px;		// max mobile / XS device width
	@query-sm-max-width: 1024px;	// max tablet / SM device width
	@query-md-max-width: 1200px;	// max "normal" desktop width
	@query-lg-max-width: 1800px;	// max "large" desktop width
									// sizes above are XL

## Available Style Names

Defining Rows and Columns

	.row, .row-xs ...
	.column, .row-xs ...
	.row.reverse, .row-xs.reverse ...
	.column.reverse, .column-xs.reverse ...

Defining column sizes

	.col-xs, .col-xs-1 ... .col-xs-@{grid-columns}
	.col-sm, .col-sm-1 ... .col-sm-@{grid-columns}
	.col-md, .col-md-1 ... .col-md-@{grid-columns}
	.col-lg, .col-lg-1 ... .col-lg-@{grid-columns}
	.col-xl, .col-xl-1 ... .col-xl-@{grid-columns}

Offset for column sizes

	.col-xs-offset-1 ... .col-xs-offset-@{grid-columns}
	.col-sm-offset-1 ... .col-sm-offset-@{grid-columns}
	.col-md-offset-1 ... .col-md-offset-@{grid-columns}
	.col-lg-offset-1 ... .col-lg-offset-@{grid-columns}
	.col-xl-offset-1 ... .col-xl-offset-@{grid-columns}


Hiding columns in a specific screensize

	.hidden-xs, .hidden-sm, .hidden-md, .hidden-lg, .hidden-xl
	.hidden // generally hidden

Showing columns in a specific screensize

	.show-xs, .show-sm, .show-md, .show-lg, .show-xl

Flex `justify-align` and `text-align`

	.justify-start, .justify-start-xs ...
	.justify-center, .justify-center-xs ...
	.justify-end, .justify-end-xs ...	
	.justify-space-around, .justify-space-around-xs ...
	.justify-space-between, .justify-space-between-xs ...

Flex `align-items`

	.align-top, align-top-xs ...
	.align-center, align-center-xs ...
	.align-bottom, align-bottom-xs ...

Flex `order`

	.order-first, order-first-xs ...
	.order-last, order-last-xs ...
	.order-initial, order-initial-xs ...

## Creating the CSS files

	# install less compiler
	npm install -g less less-plugin-clean-css
	
	# create compiled files
	lessc flexboxgrid.less flexboxgrid.css
	lessc --plugin=less-plugin-clean-css flexboxgrid.less flexboxgrid.min.css