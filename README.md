# d3 Learn

A collection of lecutre notes and coding example of d3 from [https://www.udemy.com/course/learn-d3js-for-data-visualization/](https://www.udemy.com/course/learn-d3js-for-data-visualization/) course

## Table of contents

1. [Introduction](#introduction)
2. [Javascript and SVG Fundamentals](#js-svg-fund)
3. [D3 Fundamentals](#d3-fund)
4. [Getting to know Scales](#scales)
5. [Animations and Interactivity](#anim-int)
6. [Layouts](#layouts)
7. [Maps](#maps)
8. [Wrapping up](#wrapping)

----

### Introduction <a name="introduction"></a>

#### Setting up a Local Server

- D3.js is a client side library that works alongside with HTML, CSS and JavaScript. It’s important to have an editor that supports all 3 in order to use it.
- While D3 is used on the browser, we’ll be requesting data from external sources which requires a server. You can not open up HTML files directly in the browser.
- I recommend using WebStorm by JetBrains. It is a premium editor that will take care of creating a server for you. This will allow you to focus more on your code.
- A free alternative is XAMPP. XAMPP is a program that creates a server and bundles other programs useful for web development. It’s not required to use or know those programs for D3.

#### Understanding D3 & Data Visualization

- Data visualization is the ability to tell a story or an idea through visuals and graphics. As the old saying goes, “A picture is worth a thousand words.”
- Data visualizations can help users explore patterns in their data and even notice disruptions.
- 5 tips for creating great visualizations are: Understanding your audience, choosing an appropriate visual, remove clutter, draw attention using shape size & color, and lastly telling a story.
- D3 stands for data driven documents. It’s important to understand that data is what drives the visualization, NOT the other way around.

### Javascript and SVG Fundamentals <a name="js-svg-fund"></a>

[Click here to go to code examples](javascript_and_svg_fundamentals/README.md)

#### JavaScript Arrays & Objects

- Arrays are a way to store multiple values in 1 variable. Arrays can hold any type of data including numbers, strings, Booleans, functions and objects.
- Arrays will automatically assign each value inside it a position. A position is a way to reference a value in the array. Positions start at 0 and go up as more values are added.
- Objects are similar to arrays that can hold multiple values in a single variable. The difference is that you have to name your values along with the value.

#### What is SVG

- SVG stands for Scalable Vector Graphics. It’s a special image format rather than the traditional jpg, jpeg, gif, png and bmp extensions.
- SVG images are created and edited through code. Not something that can necessarily be created sing cameras or image manipulation software like Photoshop.
- What makes SVG so great is that you can resize images without loss of quality. Image maintain their consistency and shape without having pixelated edges.
- SVG images require a lot of resources so you should only use them for basic images.

#### Creating SVG Images

- To create an SVG image you use the `<svg>` element. Most web browsers support SVG images by default so you shouldn’t face any compatibility issues.
- SVG images can have CSS classes and JavaScript events applied to them. This makes them easier to work with rather than a plain image.
- Not all CSS properties are supported. Some elements related to SVG require certain values and properties. You’ll learn what those are throughout this course.

#### SVG Rectangles

- SVG rectangle elements require that you set the width and height attributes. Otherwise nothing will appear on the screen.
- The fill attribute allows you to change the color of a SVG shape. You can’t use the background-color property on a SVG element. It will be ignored. The value for the fill can be named colors, rgb, hex and hsv.
- The stroke property will apply a border around a shape. Just like the fill property, this can only be applied to shapes. You also need to set the stroke-width or else the stroke won’t appear.

#### SVG Circles, Ellipses, and Lines

- The circle element requires that you define the r attribute which will set its radius. The radius is the distance from the center of the circle to any of it’s edges.
- The coordinate system works a bit differently. Circles are moved from their center points so you need to use the attributes cx and cy appropriately.
- An ellipse works similar to the circle element, but you’re required to set the radius for the x and y axis.
- Lines require that you set 2 coordinates which can be set using x1, y1, x2, and y2. Lines don’t have a fill so you need to use the stroke attribute to set the color.

#### SVG Polygons & Polylines

- Polygons are shapes with 3 or more straight sides. With the SVG polygon element you can create complex shapes.
- The polygon element requires 1 attribute which is the points. The points must be a set of coordinates where SVG will take care of drawing lines between them in order.
- Polylines are similar to polygons except polylines will not be closed. Despite the name, polylines will also have a fill. Set the fill attribute to none to have no fill.

#### SVG Paths

- Path elements allow you to create complex shapes. You can create sides that are either straight or curved.
- You are also allowed to create multiple shapes using one element.
- The path element works differently than the other shapes. You are required to input commands along with your coordinates to instruct SVG how to draw your shapes.
- There are 2 types of commands which are absolute and relative. Absolute commands are created using uppercase letters. Relative commands are created using lowercase letters.

#### SVG Text

- The text element allows you to create text inside SVG. Your text may not appear unless you set the x and y coordinates.
Naturally, SVG will not be able to break your text into multiple lines. In these cases you may want to use the tspan element to create multi line text.
- You can use regular HTML inside the text element, but you may need to apply special attributes in order for them to work. 

#### SVG Definitions and Groups

- Definitions allow you to create reusable elements. The benefit is that you won’t have to input the same values each time. Just define it once and you’re set!
- Any elements defined inside a definition will not be displayed. You have to use the use element and pass in the ID of the definition in order to display it.
- To group multiple elements together you can use the g element. The g element can hold any kind of shape and allows you to manage complex shapes easier.

#### SVG Text Paths

- You can create fancy text effects using text paths. Text paths allow you to use paths for text to be written on.
To create a text path you must first create a definition using the path element. You can use any commands and coordinates you want.
- Then you need to apply the textPath element to the text element and pass in the ID. The text must also be inside this element for the path to take effect.

#### SVG Clip Paths

- Clip paths allow you to hide certain parts of a shape using custom paths. Anything inside will appear while anything outside will disappear.
- Clip paths only apply to elements they’re applied to. If a shape that doesn’t have a clip path applied to it, but is touching the clip path, then it will still remain unaffected.

#### Creating SVG Elements with Illustrator

- Illustrator can be used to create SVG images. Just make sure you select svg as the file format when exporting.
- SVG files will have special attributes when you’re creating them as a separate file. This is just for the browser to better understand everything inside.
- D3 is used with SVG to create graphs and charts so be prepared to use it when we get started in the next section!

### D3 Fundamentals <a name="d3-fund"></a>

[Click here to go to code examples](d3_fundamentals/README.md)

#### Setting Up

- It’s always good practice to set the character encoding of your HTML documents. When working with D3 you’ll be dealing with a lot of data so it’s important that everything works as intended.
- Github is a site that allows you to store and share code with other developers. Most libraries are hosted on Github.
- Most libraries come with a minified version which is meant for production when you’re finished your project. Use the standard version during development.
- D3 is split into multiple libraries for developers who only want to load what they’re going to use. The main library includes everything at once for your convenience.

#### Selections

- As far as D3 is concerned, data is only text and numbers. Other types of data such as images, audio files, and videos will not work with D3 as “data”.
- D3 bridges the gap between your data and the visualization (the HTML and CSS). 
- Selections are objects that represent the HTML on your page. D3 will take care of creating these objects and fill them with properties/methods for you to use.
- If you call the append() method, then the selection will also be updated to the element created.

#### Manipulating Selections

- Transformation methods are functions that change how an element looks internally. This includes attributes or the elements inside it.
- The attr() method will add the attribute you pass in. It’s important to note that this will completely override an attribute if it already exists.
- A better alternative to adding classes to an element is by using the classed() method. If a class exists, then it will not be removed if you try to add it.
- You should always make sure you know what’s being returned. Some methods will return the current selection or an entire new one. Check the documentation to make sure.

#### Binding Data

- D3 has something called a waiting room when you bind data to an element. If data can’t be bound to an element, then the data will be placed inside the waiting room.
- To access the data in the waiting room you need to call the enter() function. This will begin looping through each piece of data.
- The minute you create an element in the loop, D3 will bind the current piece of data to that element. This is done automatically for you.
- It’s always good practice to put the data into the waiting room rather than having elements prepared already.

#### Displaying Data

- Each element has access to the data it’s binded to. You can use this as an opportunity to change the outcome of the element.
Each transformation function can accept an anonymous function which will passed the current data in the loop.

#### Loading Data Externally

- D3 supports 3 file formats which are plain text, csv and json. You can load each of these using functions provided by the D3 request library.
- CSV files are comma separated values. Each line is considered a row. Each comma separated value is considered a column. The first row is used as the column names.
- D3 takes the time to convert CSV data into objects and arrays depending on how it’s formatted.
- JSON files hardly get affected as they’re objects and arrays to begin with. It’s preferable to use JSON code rather than CSV for consistency.

### Getting to know Scales <a name="scales"></a>

[Click here to go to code examples](scales/README.md)

#### First Steps

- D3 can be used to create any type of visualization. It’s not biased towards nay chart or graph.
- Adobe color is a tool that allows you to find great color combinations and even build your own.
- You can use the data to change the outcome of the bar/chart. Most commonly used to manipulate the height or height.

#### Random Data

- Generating Random data can help battle test your graph as it allows you to cover more scenarios.
- There are situations where clients may not be able to provide you data so you’ll be responsible for generating dummy data in the mean time.
- The D3 random library takes care of generating random data for you.

#### Using SVG

- Moving SVG elements requires that you change their x and y coordinates. The X coordinate goes from left to right and the y coordinate goes from top to bottom.
- If you’re reusing values, then you should store it in a variable. This makes it easy to change later on if you ever need to.
- Labels are a way to identify a shape. Users will be able to better understand compare your visualization if you provide labels.
- Text anchoring is special to SVG. You can determine whether text gets pushed form its side or center point.

#### Scatter Plot

- Scatter plots allow you to chart large amounts of data. They are circles that represent 2 pieces of data. They can also vary in size to show more impact over others.
- Creating a scatter plot is similar to creating a bar graph. You create the elements, bind the data, create more elements for the data and add details.
- You can use the join() function to combine arrays to strings. This can be useful for displaying coordinates stored in arrays.
- Math is used to position and set the size of elements. D3 can take care of the more complex operations so you don’t have to.

#### Scales

- Scales are functions that take your data and will lower or increase the values so that they can be used for visualization.
- The input domain is the original set of data. It’s the highest and lowest numbers in your data.
- The output range is the numbers that the original data should be scaled to. These would usually be size of the viewing area.
- The D3 array library is a utility library that provides functions for working with arrays no matter how complex. It’s included in the core by default so you don’t need to do anything to set it up.

#### Applying Scales to Visualizations

- The d3.max() and d3.min() functions can be passed in accessor functions for complex array and object structures.
- An accessor function is a function that returns a value that’s used for grabbing certain data from an object or array.
- Adding padding to your visualizations is common so that shapes and text don’t get cut off from the viewing area.
- You can reverse the range and D3 will take care of scaling the values appropriately for you.

#### Exploring More Scales

- D3 provides various scales for various scenarios. An official list of scales can be found on the D3 Scales library.
- Each scale can be used for scaling different types of shapes such as the scaleSqrt() function for circles.
- Some scales are used for data that don’t contain numeric values such as colors or categorical data.

#### Time Scales

- Dates in your data will most likely come in a format that neither D3 or JavaScript can understand. D3 only works with Date Objects.
- There are a set of functions that will take care of reading your formatted dates and converting them into date objects to use with scales and vice versa.
- MomentJS is also a popular library for converting dates. You can use this if you’re comfortable with it.
- D3’s time scale will read your dates and convert them into numbers that can be used to visualize your data.

#### Adding an Axis

- An axis is a line with ticks that provide a way to visually measure the distance between certain points in a graph. D3 provides a set of functions for creating an axis.
- The axisTop() and axisBottom() functions are used for creating a horizontal axis. The axisLeft() and axisRight() functions are used for creating a vertical axis.
- Unlike scales, these functions will draw the SVG elements for you. It’s good practice to store these generated elements inside a group so they can be moved and managed easily.
- You can use CSS to refine the outcome of your SVG shapes. The more cleaner a shape looks, the more resources is required to render it.

#### Refining the Axis and adding the Y Axis

- The ticks() function allows you to set a number of ticks an axis should have. The number will only be taken as a suggestion.
- The tickValues() function will allow you to completely control how many ticks are outputted along with the actual values themselves. D3 will take the time to space them out.
- The tickFormat() function will allow you to format the text that gets outputted for each tick. You are provided the data for each tick so you can manipulate it appropriately.

### Animations and Interactivity <a name="anim-int"></a>

[Click here to go to code examples](animations_and_interactivity/README.md)

#### Ordinal Scales

- Ordinal scales are used to convert categorical data into numbers that can be used for your visualizations.
- The definition of ordinal is relating to a “thing’s” position in a series.
- D3 will evenly distribute your ordinal data. It’s important to note that it will apply padding at the end.
- A band is a specific set of numbers in a range. The set of numbers are usually distributed evenly in a pattern. Not always, but that’s usually the case.

#### Refining the Bar Graph

- You can use numeric data as ordinal data if you wish. Instead of using the numbers themselves, you can use their index.
- The band width is the distance between number in the band range. D3 provides a function called bandwidth() which will calculate this for you without the padding.
- Band scales were made specifically for bar charts so it’s recommend you use them.

#### Updating the Bar Graph

- There are 3 situations you’ll find yourself in when it comes to updating data. This can be a change in your original date, an addition or a removal.
- Changes in data usually occur during an event. By default, D3 supports all JavaScript events by using the on() function on a selection.
- The reverse() function is a JavaScript array function that will take care of reversing the values in your array.
- You can bind your data to the elements again to let D3 be aware of the change. You will have to redraw only the elements affected and only change the attributes that were affected.

#### Transitions and Animations

- Applying a transition is as simple as applying the transition() function your current selection. D3 will take care of animating the attributes for you.
- Transitions can only be applied to attributes that currently exist. Otherwise there will be no animation applied.
- You can control the duration of your transition by applying the duration() function. The length of time is measured in milliseconds.
- You can delay a transition by applying the delay() function. This is also measured in milliseconds. Be careful with your delays as it can be easy to ruin the user experience with long delays and animations.

#### Updating the Data

- If your data changes, then your visualization will not reflect that accurately. You’ll need to update the domain before you do anything else. Just call the domain() function again and pass in the new minimum and maximum values.

#### Reinforcing Transitions and Animations

- The axis needs to be updated when your data changes drastically. If not, then the data can be inaccurately read.
- You do not need to pass in the scales again as D3 will be able to detect those changes for you and update the axis appropriately.
- You are allowed to animate the axis by chaining the transition(), delay(), and duration() functions.

#### Refining the Scatterplot

- Clip paths allow you to hide portions of a shape that appears outside of its viewing area.
- It’s more efficient to group your elements together and then apply a clipping path rather than applying clip paths to each element individually.
- Transitions have events called start and end. The start event is triggered when the transitioned begins. The end transition event is triggered when the transition ends. Each element will have their own transition events.
- You can have multiple transitions occurring on the page. However, you can’t have multiple transitions applied to the same element at the same time or else the previous transitions will be cancelled.

#### Adding Data

- When you add new data, you need to update your scales domain for the new minimum and maximum values.
- The data() function returns a selection. The selection being the elements that have data binded to them.
- The elements that have data binded to them and the elements you create after moving them from the waiting room are 2 different selections.
- You can merge separate selections by calling the merge() function. This function must be chained after a selection and the selection it will be merged with must be passed into the function.

#### Removing Data

- D3 has an exit mode which will store references to elements that have no data bound to them. You can call the exit() function loop through these elements.
- If you apply the remove() function to a transition, then the function will wait until the transition is finished.
- Data joins are the process of binding a value in your data to an element. It’s the connection between the data in your array and elements on the page.
- By default, D3 will use index ordering which means the first value in the array is bound to the first element on the page. So on and so forth.

#### Mouse Hovers

- D3 supports all default JavaScript events including clicks and hovers.
- The on() function is provided the data and index which contains the value to each element in the array.
- JavaScript animations and transitions give you more power as opposed to CSS. Use JavaScript if you need that power and flexibility. Otherwise, use CSS.
- Set the CSS property pointer-events to none if you don’t want events applied to a certain element.

#### Sorting

- The d3.ascending() function will sort data and elements from smallest to biggest.
- The d3.descending() function will sort data and elements from biggest to smallest.
- You can give your transitions names to prevent collisions. This will mean you will have to interrupt animations manually by using the interrupt() function.

#### Fun with Tooltips

- There are 3 solutions for creating tooltips. The first is by using the text SVG element. This element can’t be customized, but it’s the simplest solution.
- You can create tooltips using SVG, but this is the most complex solution since SVG has a complex shape and coordinate system.
- The final solution is to just use plain HTML. The CSS position properties make it easy to create tooltips. This is one of the solutions where using HTML and SVG is ideal.

### Layouts <a name="layouts"></a>

[Click here to go to code examples](layouts/README.md)

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

### Maps <a name="maps"></a>

[Click here to go to code examples](maps/README.md)

#### GeoJSON Overview

- GeoJSON is JSON that contains coordinates that can be used to draw maps.
- It’s recommended you verify the contents of your GeoJSON code before you use it. The geojson.io tool can help you fix and verify your changes.

#### Drawing the Map & Projections

- The D3 geo library will take care of creating and drawing maps for you.
- Projections are formulas on how a 3d map looks on a 2D plane. There are various projections and standards on the d3 geo projection library page.
- Maps are drawn as is. If you would like to scale down the map, then you need to use the scale() function. You can use the translate() function to move the map as well.
- It’s preferred to store your GeoJSON code inside a separate file since there are so many coordinates.

#### Choropleth Maps

- Choropleth maps are maps that use color to highlight data between states. Example: To show heat, you can use a dark shade of red to display heat intensity.
- There is a tool called color brewer that will generate shades of colors for your maps.
- It’s important to learn how to combine 2 data sources. You will most likely come across situations where you have the data for the map and actual data in separate files.

#### Adding Cities

- Cities help make reading maps more clearer for users. Placing them on your map can make it easier to navigate around.
- The projection() function returns an array containing the x and y coordinates.
- The Math.sqrt() function is perfect for calculating the radius of a circle.

#### Panning the Map

- Panning is the ability to move a map in any direction without distorting the view.
To get the current offset you can use the projection.translate() function which returns an array of the current coordinates.
Since the coordinates system for SVG is top to bottom/left to right, then the values will most likely go in the opposite direction you’d like to go.
Panning only works well for maps that are zoomed in so be sure to increase the scale and add a transition to your panning.

#### Dragging the Map

- The D3 drag library is able to detect drag events. This includes touch on mobile devices.
- There’s a special property called d3.event that contains information about the drag event. This is not to be confused with the event object passed into javascript events.
- The d3.event.dx and d3.event.dy properties contain the distance that was dragged. The starting point is the offset for the projection.
- Dragging is only applied to the shape it’s added to. One simple track to make dragging available everywhere is to add an invisible shape.

#### Zooming

- The D3 drag library can also handle zooming. Natural zooming and panning needs to be in sync with unnatural zooming and panning.
- You need to use the translateBy() function to move the map when panning is done in an unnatural manner.
- You need to use the scaleBy() function to zoom  the map when zooming is done in an unnatural manner.

### Wrapping up <a name="wrapping"></a>

[Click here to go to code examples](wrapping/README.md)

#### Responsive Charts

- There are 2 solutions for creating responsive charts which is using SVG attributes or JavaScript events and redrawing the chart. SVG attributes is the more modern and elegant solution.
- The viewBox attribute determines the viewing area of your chart. The first 2 values are the starting points and the next 2 are width/height of the area.
- The preserveAspectRatio attribute is used to help with scaling on various devices. The xMidYMid ratio is usually the best for most charts/graphs.
