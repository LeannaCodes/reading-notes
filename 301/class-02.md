# What does .map() return?

.map() loops through an array and returns something else. 

.map() loops through an array and asigns it as something else. For example: 

given the code below, we use the map() function to take an array of numbers and double their values. We assign the new array returned by map() to the variable doubled and log it: 

```
const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map((number) => number * 2);
console.log(doubled);
```
This logs this code into the console: `[2, 4, 6, 8, 10]`
 
# If I want to loop through an array and display each value in JSX, how do I do that in React?

## Rendering Multiple Components 

You can build collections of elements and include them in **JSX** using **curly braces**. 

for the record, JSX stands for JavaScript XML. JSX allows us to write HTML in React. JSX makes it easier to write and add HTML in React. 

In this example, we loop through the TechEdPeeps array using the JavaScript map() function. We return a <li> element for each item. Finally, we assign the resulting array of elements to list Items: 

const techEdPeeps = [Tim, Leanna, James, Munya, Ida, V]
const listItems = techEdPeeps.map((person) => {
   return <li>{person}</li>
}
);
<ul>{listItems}</ul>

This then spits out a bullet list of people from Tech Ed. 



# Each item needs a unique what? 

# What is the purpose of a key?