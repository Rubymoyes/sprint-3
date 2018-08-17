- What happens to the layout when you resize the screen to less than 550 px. How do you think that works?

In the skeleton.css file, you find these lines of code:

-

/* For devices larger than 400px */
@media (min-width: 400px) {
  .container {
    width: 85%;
    padding: 0; }

/* For devices larger than 550px */
@media (min-width: 550px) {
  .container {
    width: 80%; }
  .column,
  .columns {
    margin-left: 4%; }
  .column:first-child,
  .columns:first-child {
    margin-left: 0; }

-

This means that when the screen is at 400px or less, the width of the .container element goes to 85 per cent, but the only thing that really changes on the page massively are the columns. If the browser has a lower resolution than 550px, then the columns that are in the .css file are set to go from their original state (1 row, 2 columns on one line) to 2 columns, 1 row, but the percentage of the column size changes. They expand and seperate, which makes it appear that they have jumped to different rows, but they haven't. The row hasn't expanded or changed, it's just the column percentage size that has changed to make them take up the entirety of the box.

It works by using the @media rule in CSS. Using media queries is the best way to design a responsive web page for different devices with different viewports, screen resolutions and devices. The size of the resolution can be specified to allow certain things to appear a certain way on the page. The @media rule also can be used to check the orientation of the page, specifying certain styles and helping with browser support. Browser support can also be specified in different rules using the -ms-, -moz- and -webkit- prefixes.