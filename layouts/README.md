
# Layouts <a name="layouts"></a>

[Click here to go back](https://github.com/pupubird/d3-learn)

#### Line Charts

- The D3 shape contains functions for creating complex shapes using the path element exclusively.
- The d3.line() function will create a function that you can use to draw complex lines. It only draws 1 line and not multiple lines.
- The datum() function will bind 1 piece of data to 1 element. There’s no need to perform looping or use the enter mode.
If your data contains negative numbers, then it’s up to you to decide how to approach that. The defined function allows you to filter values in your data.

#### Improving the Visualization

- Area charts are similar to line charts. You create the functions, then bind the data to an element and call the function to begin drawing the area.
- Areas created by drawing 2 invisible lines. Anything in between those lines gets filled in with a color.
You have the option of specifying the coordinates together or specifying them separately.

#### Pie & Donut Charts

- Pie and Donut charts are drawn by drawing the slices rather than the whole circle itself. These slices are then combined together.
- Arcs are the shapes D3 will draw for you using the d3.arc() function. Each arc has an inner radius and outer radius. By setting the inner radius, you can make pie charts into t charts.
- Layouts are functions that convert your current existing data into data that can be used to draw different types of charts.
- Radians are used to measure the degrees of angles in arcs. D3 will take care of that conversion for you.

#### Stacked Bar charts

- Stack layouts are used for creating stack charts like stack bar graphs or stack area charts.
- Stack layouts work by categorizing your data and assigning start and end positions.
- You need to call the keys() function to set the categories.

#### Force Layouts

- Nodes are a unit of data. They’re mostly used in hierarchies of data like an HTML document.
- Along with your usual data you also need to specify the relationships between the data.
- To create a force, you need to use the forceSimulation() function and pass in the different forces using the force() function. This function will determine the behavior of the visualization.
- D3 will examine the data’s coordinates and determine if the shapes are too close or too far. It will then proceed to adjust the coordinates until they’re within the boundaries set. The ticks event allows you to listen for every change.
