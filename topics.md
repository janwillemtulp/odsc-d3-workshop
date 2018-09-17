# Introduction
* visualization in general -> encoding (mapping) data to visual elements
* What - Why - How
* importance of making proper design decisions. D3 is just a means to an end
* what is D3: Javascript library for manipulating DOM elements (`HTML`, `SVG`)
* no need to know everything / use Google / start small / many resources

# Environment set up
* check everything is working (empty page, Python server)
* using standard Javascript (not ES6)

# Basics
* create inline `SVG` manually, just like `HTML`
* using `CSS` to style `SVG`, both inline and using classes
  * specific styling for `SVG`
* explain attributes and styles

# Selections
* explain CSS selectors: `.classname`, `#id`, element by showing CSS snippet
* explain select
* explain selectAll
* explain `attr()` and `style()` and method chaining
* explain `select().append()`, `selectAll().append()` and `select().remove()`

# Data
## Standard JS
* explain arrays
* explain lists of objects

## D3 and data
* explain `selection.data()`, and `selection.data(..., id-function)`
* explain `selection.enter()`
* explain `selection.exit()`
* explain `selection.merge()`
* common mistake: select by class name, but forget to add a class

## Nesting data
* explain `nest()`
* explain nested selections

## Loading data
* explain `d3.csv()`, `d3.tsv()`, `d3.json()`

```javascript
var circle = svg.selectAll("circle").data(data) // UPDATE
    .style("fill", "blue");

circle.exit().remove(); // EXIT

circle = circle.enter().append("circle") // ENTER
    .style("fill", "green")
  .merge(circle) // ENTER + UPDATE
    .style("stroke", "black");
```
* explain Javascript built-in map, filter, sort
* explain D3 data manipulation, example: d3.nest()

# Transitions
* explain `transition().attr()`
* explain `transition().style()`
* explain `delay()`
* explain `duration()`

# Scales
```javascript
scaleLinear()
  .domain()
  .range()
```
* explain `domain()`
  * explain `d3.max()`, `d3.min()`, `d3.extent()`
* explain ranges
```javascript
scaleOrdinal()
  .domain()
  .range()
```
```javascript
x.ticks(10)
```
* `category10()`

# Axes
```javascript
var xAxis = d3.svg.axis()
  .scale(x)
  .orient('left')

svg.append('g')
  .attr('class', 'y axis')
  .call(yAxis)
```

```css
.axis path, .axis line {
  fill: none;
  stroke: #000;
  shape-rendering: crispEdges;
}
```

* explain interpolators:
  * min and max
  * multiple values (diverging scales)
  * color hex values
  * pixels 
  * other interpolators, such as interpolateHsl()
  * ordinal scales
    * built-in scales: category10(), category20()
* explain types of scales: log, pow, sqrt

# SVG coordinates
* explain SVG `<g>` elements and `.transform()` attributes
* explain margin convention:
```javascript
var margin = {top: 20, right: 10, bottom: 20, left: 10};

var width = 960 - margin.left - margin.right,
    height = 500 - margin.top - margin.bottom;

var svg = d3.select("body").append("svg")
    .attr("width", width + margin.left + margin.right)
    .attr("height", height + margin.top + margin.bottom)
  .append("g")
    .attr("transform", "translate(" + margin.left + "," + margin.top + ")");

var x = d3.scale.linear()
    .range([0, width]);

var y = d3.scale.linear()
    .range([height, 0]);
```

# Interaction
* explain `click()`, `mouseover()`
* explain `d3.mouse(node)[x, y]` to detect mouse position

# Shapes
* explain `circle()`
```javascript
rect()
  .attr('x')
  .attr('y')
  .attr('width')
  .attr('height')
```
```javascript
text()
  .text()
  .attr('x')
  .attr('y')
  .attr('dx')
  .attr('dy')
  .attr('rx')
  .attr('ry')
  .style('font-size')
  .style('fill')
  .style('text-anchor')
```
* show `path()` `d()` attribute
`M1.2246467991473532e-14,-200A200,200,0,0,1,185.95529717765027,73.6249105369356L92.97764858882513,36.8124552684678A100,100,0,0,0,6.123233995736766e-15,-100Z`
```javascript
path()
  .attr('d')
  .style('fill')
  .style('stroke')
```


#  generators
```javascript  
line()
  .x()
  .y()
  .curve(d3.curveCatmullRom.alpha(0.5))
  .curve(d3.curveBasis)
  .curve(d3.curveBasisClosed)
  .curve(d3.curveBundle.beta(0.5))
  .curve(d3.curveCardinal.tension(0.5))
  .curve(d3.curveCardinalClosed.tension(0.5))
  .curve(d3.curveLinear)
  .curve(d3.curveLinearClosed)
  .curve(d3.curveStep)
  .curve(d3.curveStepAfter)
  .curve(d3.curveStepBefore)
```
```javascript
arc()
  .innerRadius()
  .outerRadius()
  .startAngle()
  .endAngle()
```
```javascript
pie()(data)
  .value() // accessor
  .startAngle() // accessor
  .endAngle() // accessor
  .sort() // sorts the pies on some criteria
  .sortValues() // sorts the values
```
```javascript
area()
  .x()
  .y0()
  .y1()
```

# EXERCISE: build your own

# Layouts ??

# Charts ??

