
# Animations and Interactivity <a name="anim-int"></a>

[Click here to go back](https://github.com/pupubird/d3-learn)

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
