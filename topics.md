# Introduction
* visualization in general -> encoding (mapping) data to visual elements
* What - Why - How
* importance of making proper design decisions. D3 is just a means to an end
* what is D3: Javascript library for manipulating DOM elements (HTML, SVG)
* no need to know everything / use Google / start small / many resources

# Environment set up
* check everything is working (empty page, Python server)
* using standard Javascript (not ES6)

# Basics
* create inline SVG manually, just like HTML
* using CSS to style SVG, both inline and using classes
  * specific styling for SVG
* explain attributes and styles

# Selections
* explain CSS selectors: .classname, #id, element by showing CSS snippet
* explain select
* explain selectAll
* explain .attr() and .style() and method chaining
* explain select().append(), selectAll().append() and select().remove()

# Data
* explain arrays
* explain lists of objects
* explain selection.data(), and selection.data(..., id-function)
* explain selection.enter()
* explain selection.exit()
* explain selection.merge()

## Loading data
* explain d3.csv(), d3.tsv(), d3.json()

```
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
* explain attribute transition
* explain style transition
* explain delay
* explain duration

# Scales
* explain linear scales
* explain domains
  * explain d3.max(), d3.min(), d3.extent()
* explain ranges
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
* explain SVG G elements and transoform attributes
* explain margin convention

# Interaction
* explain click, mouseover
* explain d3.mouse to detect mouse position

# Shapes
* explain circle
* explain rect
* explain text
* explain path
* explain path generators
  * explain line
    * explain curves (line interpolation)
  * explain arc
  * explain pie
  * explain area

# EXERCISE: build your own

# Layouts ??

# Charts ??

