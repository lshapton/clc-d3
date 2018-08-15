# Canada Learning Code - D3 workshop

1. Create an SVG

Before you can draw anything, you must create an SVG element. The SVG element is a canvas on which your visuals are rendered. Remember to specify width and height of the SVG element.

2. Create a scatterplot

First let's plot temperature by month.

To create a plot for each month:

```
svg.selectAll("circle")
   .data(dataset)
   .enter()
   .append("circle")
```

First, select all `circles` inside the svg (currently, there are none... but, just wait!). Next, `data(dataset)` sees there are 12 values in the dataset and passes this values to `enter()` which creates a placeholder for each value, if a circle doesn't exist. Finally, `append("circle")` inserts a circle for each placeholder/value.

Next, we define the cx and cy values to plot the circle on the graph. In our example, months will appear along the x-axis and temperature will be plotted along the y-axis.To map values to our svg, we can use a scale.

**Scales** are functions that map an input domain to an output range. The input range for our temperature values is -3 to 21°C. The output domain is the height of our svg plus padding. For SVGs, the top left corner is considered to be (x=0,y=0). If we want smaller y values to appear at the bottom of our svg, we can map smaller input values to larger y values using our scale. We will use a linearScale for our temperature values.

For our x-axis, we can use a ordinal scale. `scaleBand` is a type of ordinal scale. For `scaleBand`, the range is the array representing the list of months and the domain is the width of our svg plus padding.

2. Add axis and label

Much like its scales, D3’s axes are actually functions whose parameters you define. There are four different axis function constructors, each one corresponding to a different orientation and placement of labels: d3.axisTop, d3.axisBottom, d3.axisLeft, and d3.axisRight. We will use d3.axisBottom for our x-axis and d3.axisLeft for our y-axis. We pass our scales in as an argument to the axis functions.

To draw the axis on the page, append a container to you SVG and call your axis function. Apply a transformation to position your axis correctly on the page. [You can add ticks and format them as well](https://github.com/d3/d3-axis).

To add labels, add text elements to your SVG element.

3. More visualization

Change the radius of your circle, to represent another datapoint like rainfall. Hint: A circle SVG has a r attribute and D3 has a rScale.

5. Adding events

Bonus: Add tooltips when hovering over each circle. There are many ways to do this! Try adding and removing classes when hovering over circles.

## Resources:
- Scott Murray's Interactive Data Visualization for the Web: An Introduction to Designing with D3
