---
title: "My First Post"
date: 2022-11-20T09:03:20-08:00
draft: true
---
﻿<a name="_66mewcur1gr7"></a>**Himanshu Singh**

<a name="_78kyao793hme"></a><a name="_famfozupfpti"></a>**Higher Order and Callback Functions - JavaScript**

JavaScript, a versatile and widely used programming language, provides developers with powerful tools for creating dynamic and efficient code. In this blog post, we will delve into the essential concept of Higher Order Functions that can elevate your JavaScript Programming Skills.

In this guide, you’ll find everything you need to know to get started with Higher Order Function in JavaScript, including:

- What Higher Order Functions are and why it’s important.
- The 3 different types of Built-in Higher Order functions in JavaScript.
- What are Callback Functions and how do they work.
- Best practices to follow in order to succeed with Higher Order and Callback Functions.

Let us deep dive into each topics one by one :
##
## <a name="_1bb44ytmk3ma"></a><a name="_lqzr7cqrmrh1"></a>**What are Higher Order Functions and why is it important?**
In order to understand this concept, we first have to understand what First-Class Functions are in JavaScript.

- **First-Class Functions :** In JavaScript functions are a special type of objects. They are called *Function* objects. For example : 



`	`*function greeting() {*

`		`*console.log(‘Hello World’’);*

`		`*}*

`	`*//Invoking the function*

`	`*greeting(); 	//prints ‘Hello World’*

In JavaScript, everything you can do with other types like object, string, or number, you can do with functions. You can pass them as parameters to other functions (callbacks), assign them to variables and pass them around etc. This is why functions in JavaScript are known as First-Class Functions.

- **Assigning function to variables** : In JavaScript, you can assign functions to variables. For example : 



`			`*const square = function(x) {*

`				`*return x \* x;*

*}*

*//prints 25*

*square(5);*

- **Passing Functions as Parameters :** We can pass functions as parameters to other functions. For example : 



`		`*function formalGreeting() {*

`			`*console.log(“How are you?”);*

`		`*}*

`		`*function casualGreeting() {*

`			`*console.log(“What’s up?”);*

`		`*}*

`		`*function greet(type, greetFormal, greetCasual) {*

`			`*if(type === ‘formal’) {*

`			`*greetFormal();*

`		`*} else if(type === ‘casual’) {*

`			`*greetCasual();*

`			`*}*

`		`*}*
##
<a name="_k2jc3cng41n"></a>		*//prints ‘What’s up?’*

`		`*greet(‘casual’, formalGreeting, casualGreeting);*

Now that we know what first-class functions are, let’s dive into Higher-Order Functions in JavaScript.

- **Higher-Order Functions :** 

Higher order functions are functions that operate on other functions, either by taking them as arguments or by returning them. In simple words, A Higher-Order function is a function that receives a function as an argument or returns the function as output.

For example : Array.map, Array.filter and Array.reduce are some of the Higher-Order functions built into the language.

Let’s look at an example : 

**Scenario :** Let’s say we have an array of numbers and we want to create a new array which contains double of each value of the first array. Let’s see how we can solve the problem with and without Higher-Order Function.



**Without Higher-Order Function :**

**		*const arr1 = [1, 2, 3];*

`		`*const arr2 = [];*

`		`*for(let index = 0; index < arr1.length; i++)
`		`{*

`			`*arr2.push(arr1[i] \* 2);*

`		`*}*

`		`*//prints [2, 4, 6]*

`		`*console.log(arr2);*

**With Higher-Order Function (map):**

**		*const arr1 = [1, 2, 3]*

`		`*const arr2 = arr1.map(function(item) {*

*return item \* 2*

*});*

*console.log(arr2);*

\*In this example, **map** is a Higher Order Function that takes a different function as an argument(callback function).

- **Why it’s so important :** 

**	Let's explore why Higher Order Functions are so important in JavaScript.

1. **Data Abstraction :** Higher Order Functions allow you to abstract away complex logic into separate functions, promoting code modularity. This not only makes your code more readable but also facilitates easier maintenance and debugging.
1. **Code Reusability :** By accepting functions as arguments or returning them, HOFs enable you to write more reusable code. Functions become building blocks that can be combined in various ways to perform different tasks.

1. **Support for Asynchronous Programming :** In the context of asynchronous programming, Higher Order Functions play a crucial role in handling callbacks, promises, and other asynchronous patterns. Functions like *setTimeout, setInterval,* and *fetch* are examples of Higher Order Functions used in asynchronous scenarios.






## <a name="_bec4yf4h0v3t"></a>**The 3 different types of Built-in Higher Order function in JavaScript**

Let us talk about the 3 most widely used built-in Higher Order Function in JavaScript, i:e **Array.prototype.map, Array.prototype.filter** and **Array.prototype.reduce.**

1. **Array.prototype.map:** The **map()** method creates a new array by calling the callback function provided as an argument on every element in the input array. The **map()** method will take every returned value from the callback function and creates a new array using those values.

The callback function passed to the **map()** method accepts 3 arguments: ***element, index,*** and ***array***.

Let’s understand it with an example:

**Scenario:** Let’s say we have an array containing the birth year of different persons and we want to create an array that contains their ages. 

`		`*const birthYear = [1975, 1997, 2002, 1995, 1985];*
\*


`		`*const ages = birthYear**.map**(year => 2018 - year);*

`		`*//prints [43, 21, 16, 23, 33]*

`		`*console.log(ages);*


1. **Array.prototype.filter:** The **filter()** method creates a new array with all elements that pass the test provided by the callback function. The callback function passed to the **filter()** method accepts 3 arguments: **element, index,** and **array.**

The callback function passed to the **filter()** method accepts 3 arguments: ***element, index,*** and ***array***.

Let’s understand it with an example:

**Scenario:** Let’s say we have an array which contains objects with name and age properties. We want to create an array that contains only the persons with full age (age greater than or equal to 18).

`		`*const persons = [*

`			`*{ name: 'Peter', age: 16 },*

`  			`*{ name: 'Mark', age: 18 },*

`  			`*{ name: 'John', age: 27 },*

`  			`*{ name: 'Jane', age: 14 },*

`  			`*{ name: 'Tony', age: 24},*

`		`*];*

`		`*const fullAge = persons.filter(person => person.age >= 18);*

`		`*console.log(fullAge);*


1. **Array.prototype.reduce:** The reduce method executes the callback function on each member of the calling array which results in a single output value. The **reduce** method accepts two parameters: 1) The reducer function **(callback)**, 2) and an optional **initialValue**.

The reducer function (callback) accepts four parameters: ***accumulator***, ***currentValue***, ***currentIndex***, ***sourceArray***.

If an initialValue is provided, then the accumulator will be equal to the initialValue and the currentValue will be equal to the first element in the array.

If no initialValue is provided, then the accumulator will be equal to the first element in the array and the currentValue will be equal to the second element in the array.

Let’s understand it with an example:

**Scenario:** Let’s say we have to sum an array of numbers:

`		`*const arr = [5, 7, 1, 8, 4];*

`		`*const sum = arr.reduce(function(accumulator, currentValue) {*

*Return accumulator + currentValue}, 10);*

*//prints 25*

*console.log(sum);*

\*	

Every time the reducer() is called on each value in the array, the accumulator keeps the result of previous operation returned from the reducer function, and the currentValue is set to the current value of the array. In the end the result is stored in the sum variable.

We can also provide an **initial value** to this function: which in this case is **10**


## <a name="_quostgcu0ymk"></a>**What are Callback Function and how do they work**

- **Callback Function:** 

In JavaScript, a callback function is a function that is ***passed as an argument to another function*** and is executed after the completion of some asynchronous operation or at a specified time. Callbacks are a fundamental concept in JavaScript, especially in scenarios where you're dealing with asynchronous code, such as handling events, making AJAX requests, or working with timers.

Let us understand **Synchronous** and **Asynchronous Callback** with the help of examples:

1. **Synchronous Callback:**


*function synchronousOperation(callback) {*

`  `*console.log("Doing some synchronous operation...");*

`  `*callback();* 

*}*

*function callbackFunction() {*

`  `*console.log("Callback function executed!");*

*}*

*// Invoking*

*synchronousOperation(callbackFunction);*

`	`\*In this example, synchronousOperation is a function that takes a callback function as an argument and calls it synchronously.

1. **Asynchronous Callback:**

**			
**
`			`*// **Asynchronous callback** example using **setTimeout***

*function asynchronousOperation(callback) {*

`  				`*console.log("Doing some asynchronous operation...");*

`  			`*setTimeout(function () {*

`    			`*callback();* 

`  			`*}, 2000);*

*}*

*function callbackFunction() {*

`  			`*console.log("Callback function executed!");*

*}*

*// Invoking*

*asynchronousOperation(callbackFunction);*

**\***In this example, asynchronousOperation simulates an asynchronous operation using setTimeout. The callback function is executed after a 2000 milliseconds (2 seconds) delay.



- **When to use Callback Function:**

You may use Callback function when you need to take action after an asynchronous process has finished, callbacks can be helpful or when you want to separate the code that executes an asynchronous operation from the code that handles the results of the operation, you should generally use a callback function. Your code may become more modular and understandable as a result.

Below are some specific cases where you might want to use a callback function:

- When making an asynchronous API call.
- When listening for events.
- When running a long-running task.
- When working with promises.
##
##
## <a name="_ntjesj4x7jf7"></a><a name="_7ptdyvjjbop"></a><a name="_joca4pr5q3lg"></a>**Best practices to order to succeed with Higher Order and Callback Functions**

In conclusion, understanding and effectively implementing higher-order functions and callback functions are crucial skills for JavaScript developers. By following best practices, developers can write code that is not only readable and maintainable but also robust and scalable. Clear and descriptive naming, proper documentation, and error handling contribute to the overall quality of the code.

Avoiding callback hell by modularizing code, using arrow functions judiciously, and considering alternative approaches like Promises or **async/await** for asynchronous operations are essential for managing complexity in larger codebases. The principles of functional programming, such as immutability and focusing on a single concern, further contribute to code quality.

Consistency in coding style, handling errors gracefully, and ensuring testability are key aspects of writing reliable callback functions. Striking a balance between the concise syntax of arrow functions and the readability of traditional function declarations is crucial for code maintainability.

Ultimately, mastering higher-order and callback functions empowers developers to create code that is not only efficient but also adheres to best practices, making it easier to collaborate with others and maintain over time.

