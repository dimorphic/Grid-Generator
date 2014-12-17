Grid-Generator
==============

GridGenerator is a SASS mixin meant to replace all grids :) From Twitter Bootstrap to Foundation, 960, etc all of them come with a lot of classes that pollute the code.

Using the very cool ‘map’ property that came in SASS v3 http://sass.logdown.com/ we can now create pretty objects to generate only specific grids / grid classes / grid styles. 

Example: 

```css
$gridSetup: (
	columnCount: 2
);

@include generateGrid($gridSetup);
```
Turns into 
```CSS
.grid {
  width: inherit;
}

.grid [class*='col-'] {
  float: left;
  width: 100%;
}

.grid .col-2 {
  width: 50%;
}
```

A more complicated example would look like this: 

```css
$gridSetup2: (
	mobile: (
		columnCount: 2,
		columnDistribution: (3, 7)
	),
	tablet: (
		columnCount: 3
	),
	desktop: (
		columnCount: 6
	)
);
@include generateGrid($gridSetup2);
```
And generates this CSS
```CSS
@media only screen and (max-width: 767px) {
  .grid .col-mobile-2-3 {
    width: 30%;
  }

  .grid .col-mobile-2-7 {
    width: 70%;
  }
}
@media only screen and (min-width: 768px) {
  .grid .col-tablet-3 {
    width: 33.33333%;
  }
}
@media only screen and (min-width: 1024px) {
  .grid .col-desktop-6 {
    width: 16.66667%;
  }
}

@media only screen and (min-width: 1024px) {
  .grid .col-desktop-3-2 {
    width: 20%;
  }
  .grid .col-desktop-3-2 {
    width: 20%;
  }
  .grid .col-desktop-3-6 {
    width: 60%;
  }
}
```
