# React Docs - lists and keys
https://reactjs.org/docs/lists-and-keys.html


1.	What does .map() return?

The map() method creates a new array populated with the results of calling a provided function on every element in the calling array.

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map

2.	If I want to loop through an array and display each value in JSX, how do I do that in React?

You would want to use curly braces and assign a key in order for React to identify it.

function NumberList(props) {
  const numbers = props.numbers;
  const listItems = numbers.map((number) =>
    <li key={number.toString()}>      {number}
    </li>
  );
  return (
    <ul>{listItems}</ul>
  );
}

3.	Each list item needs a unique ____KEY

Pick a key is to use a string that uniquely identifies a list item among its siblings. Most often you would use IDs from your data as keys.

const todoItems = todos.map((todo) =>
  <li key={todo.id}>
    {todo.text}
  </li>
);

4.	What is the purpose of a key?

Keys should be given to the elements inside the array to give the elements a stable identity.

## The Spread Operator
https://medium.com/coding-at-dawn/how-to-use-the-spread-operator-in-javascript-b9e4a8b06fab

1.	What is the spread operator?

The spread operator is a useful and quick syntax for adding items to arrays, combining arrays or objects, and spreading an array out into a functionβs arguments.

In JavaScript, spread syntax refers to the use of an ellipsis of three dots (β¦) to expand an iterable object into the list of arguments.

2.	List 4 things that the spread operator can do.

The spread syntax βspreadsβ the array into separate arguments.
Copying an array
Concatenating or combining arrays
Using Math functions
Using an array as arguments
Adding an item to a list
Adding to state in React
Combining objects
Converting NodeList to an array

3.	Give an example of using the spread operator to combine two arrays.

[...["ππππ€ͺπ"]] // Array [ "ππππ€ͺπ" ]
[..."ππππππ₯°ππ€©!"] // Array(9) [ "π", "π", "π", "π", "π", "π₯°", "π", "π€©", "!" ]

const hello = {hello: "ππππ€ͺπ"}
const world = {world: "ππππππ₯°ππ€©!"}

const helloWorld = {...hello,...world}
console.log(helloWorld) // Object { hello: "ππππ€ͺπ", world: "ππππππ₯°ππ€©!" }

4.	Give an example of using the spread operator to add a new item to an array.

const fruits = ['π','π','π','π','π']
const moreFruits = [...fruits];
console.log(moreFruits) // Array(5) [ "π", "π", "π", "π", "π" ]
fruits[0] = 'π'
console.log(...[...fruits,'...',...moreFruits]) //  π π π π π ... π π π π π

5.	Give an example of using the spread operator to combine two objects into one.

const myArray = [`π€ͺ`,`π»`,`π`]
const yourArray = [`π`,`π€`,`π€©`]
const ourArray = [...myArray,...yourArray]
console.log(...ourArray) // π€ͺ π» π π π€ π€©


## Videos

### How to Pass Functions Between Components
https://www.youtube.com/watch?v=c05OL7XbwXU


1.	In the video, what is the first step that the developer does to pass functions between components?

To create a function where the state is located. Then he created a variable using the map() to create an new array.
Increment = (name) => {
Let ppl= this.state.people.map()
}

2.	In your own words, what does the increment function do?

It increments your count on an object in an array.

3.	How can you pass a method from a parent component into a child component?

By passing the parent props into the child component.

4.	How does the child component invoke a method that was passed to it from a parent component?

By calling the method in the parent.


### Bookmark and Review

#### React Tutorial through βDeclaring a Winnerβ
https://reactjs.org/tutorial/tutorial.html


#### React Docs - Lifting State Up
https://reactjs.org/docs/lifting-state-up.html


### Things I want to know more about:

How to maneuver in react and incorporate in my code.



