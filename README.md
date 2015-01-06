WTGrid
==============

With the help of WTGrid you will be able to generate whatever CSS grid you need. Unlike all CSS frameworks out there WTGrid creates only the needed styles without polluting the source code with unneeded code. 

WTGrid is full responsive and compatible with IE9+ 

SASS V3.3+ is needed

Params: 

```columnCount``` - is used to define the number of columns, everything is in %.

```columnVariations``` - used to define custom sizes for columns. ex: 2o7 will create a column thats wide as 2 columns out of 7 

``` s / m / l / xl ``` - are used with ```columnCount``` and ```columnVariations``` to setup the grid for responsive breakpoints 


Minimal setup: 

```
$gridSetup: (
    columnCount: 2
);

@include generateGrid($gridSetup);
```

Advanced setup: 

```
$gridSetup: (
	columnCount: 1 2 4 7 9 10 11,
	columnVariations: "2o7" "5o7" "3o4" "1o4" "5o11" "6o11"",
	gutter: 10px,
	s: (
		columnCount: 3,
		gutter: 20px
	),
	m: (
		columnCount: 5 7,
		columnVariations: "2o5" "3o5",
		gutter: 16px
	),
	l: (
		columnCount: 1 3 4,
		columnVariations: "1o4" "3o4"
	),
	xl: (
		columnCount: 9
	)
);
	
@include generateGrid($gridSetup);
```
