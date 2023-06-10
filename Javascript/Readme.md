## What is Javascript?

JavaScript is a `dynamic language` with `dynamic types`. Variables in JavaScript are not directly associated with any particular value type, and any variable can be assigned (and re-assigned) values of all types.

| Data Type   | Description                                                        | Example                          |
| ----------- | ------------------------------------------------------------------ | -------------------------------- |
| `undefined` | Represents an undefined value.                                     | `let variable;`                  |
| `null`      | Represents the absence of any `object value`                       | `let variable = null;`           |
| `boolean`   | Represents a logical entity and can have two values: `true` or `false`. | `let variable = true;`          |
| `number`    | Represents numeric values, including integers and floating-point numbers. | `let variable = 42;`             |
| `string`    | Represents a sequence of characters enclosed in quotes.             | `let variable = "Hello, World!";` |
| `symbol`    | Represents unique identifiers that are immutable and can be used as property keys. | `let variable = Symbol("description");` |
| `bigint`    | Represents integers with arbitrary precision.                       | `let variable = BigInt(42);`     |

<br>

## What is hoisting in Javascript?

Hoisting in JavaScript is a behavior where variable and function declarations are `moved to the top of their containing scope` during the `compilation phase`, before the code is executed. This means that regardless of where variables and functions are declared in the code, they are treated as if they are declared at the top of their scope.

There are two types of hoisting: `variable hoisting` and `function hoisting.`

`Variable Hoisting`
```javascript 
    console.log(a); // Output: undefined
    var a = 10;
    console.log(a); // Output: 10
```

`Function Hoisting`
```javascript
    greet(); // Output: "Hello!"

    function greet() {
        console.log("Hello!");
    }
```
- Variables declared using var are hoisted to the top of their scope and initialized with a value of undefined(special type).
- Variables declared using let are hoisted to the top of their scope but are not initialized with any value.
- Variables declared using const are hoisted to the top of their scope but are not initialized with any value.
 
<br>

 ## Difference between var and let keyword in javascript.

 - 'var' keyword was used in JavaScript programming whereas the keyword 'let' was just added in 2015.
 - The keyword 'Var' has a function scope. Anywhere in the function, the variable specified using var is accessible but in ‘let’ the scope of a variable declared with the 'let' keyword is limited to the block in which it is declared. Let's start with a Block Scope.
 - `let` and `const` are `hoisted but not initialized`. `Referencing` the variable in the block `before the variable declaration` results in a `ReferenceError` because the variable is in a `"temporal dead zone"` from the start of the block until the declaration is processed.
- A variable declared using ‘var’ can be redefined and even redeclared anywhere throughout its scope.

```javascript
var x = 30;
console.log(x); //prints 30
x = "Hi"; //redefining or re-assigning (works without any error)
console.log(x); //prints "Hi"
 
var y = 10;
console.log(y); //prints 10
var y = "Hello"; //Redeclaring (works without any error)
console.log(y) //Prints "Hello"
```
- A variable declared using `let` `can be redefined` within its scope but `cannot be re-declared` within its scope.
- A variable declared using `const` `cannot` be `redefined` or `re-declared` within its scope.
- Every const declaration must be initialized at the time of declaration.

<br>

## what is temporal deadzone in javascript?

The Temporal Dead Zone (TDZ) is a behavior in JavaScript that occurs `when using variables declared with let and const before they are formally declared in the code.` The TDZ is a specific period between the start of a scope and the point where a variable is declared, during which accessing the variable results in a ReferenceError.

The TDZ exists to enforce block scope and prevent the use of variables before they are declared, helping to catch potential bugs caused by accessing variables too early in the code.

Here's an example to illustrate the concept of TDZ:

```javascript
console.log(a); // ReferenceError: Cannot access 'a' before initialization
let a = 10;
```
The TDZ ends when the variable is formally declared. In this case, the TDZ ends once the let a = 10; statement is encountered. 

It's important to note that the `TDZ applies only to variables declared with let and const`, as they have `block scope`. Variables declared with `var` are `not subject to the TDZ` and have `function scope`, which allows them to be accessed anywhere within the enclosing function, even before their formal declaration (although their value will be undefined until initialized).

<br>

## What is the difference between an iterator and a generator in JavaScript? 

Iterators are one-time use, while generators can be paused and resumed.

**`Iterators`**: Iterators are objects that provide a sequence of values by implementing the Iterator protocol. They are primarily used for looping over data structures such as arrays or sets. An iterator allows you to iterate over a collection one item at a time, fetching the next item in the sequence until there are no more items left. Once an iterator is exhausted (all items have been iterated), it cannot be used again. You would need to create a new iterator to iterate over the collection again.

*CODE EXAMPLE*

```javascript
// Create an iterator for an array
const arrayIterator = (array) => {
  let index = 0;

  return {
    next: () => {
      if (index < array.length) {
        return {
          value: array[index++],
          done: false
        };
      } else {
        return { done: true };
      }
    }
  };
};

// Use the iterator to loop over an array
const colors = ['red', 'green', 'blue'];
const iterator = arrayIterator(colors);

let result = iterator.next();
while (!result.done) {
  console.log(result.value);
  result = iterator.next();
}

```


**`Generators`**: Generators are a special type of function that can be paused and resumed during execution. They use the function* syntax in JavaScript. When a generator function is invoked, it returns a generator object. This object can be iterated over using the next() method, similar to iterators. However, the key difference is that generators can be paused during execution using the yield keyword. The generator remembers its internal state, and when next() is called again, it resumes execution from where it left off, allowing you to control the flow of data. This feature makes generators useful for implementing iterative algorithms and working with asynchronous operations.

```javascript
// Generator function
function* numberGenerator() {
  yield 1;
  yield 2;
  yield 3;
}

// Use the generator to iterate over numbers
const generator = numberGenerator();

console.log(generator.next().value); // Output: 1
console.log(generator.next().value); // Output: 2
console.log(generator.next().value); // Output: 3
console.log(generator.next().done);  // Output: true
```
Notice that **`*`** is not by mistake but a way to write generator function.

In this example, the ***numberGenerator*** is a generator function that yields a sequence of numbers. Each time next() is called on the generator, it returns an object with a value property representing the yielded value and a done property indicating whether the generator has completed. The generator can be paused and resumed, allowing for more fine-grained control over the iteration process.

yield pauses the state while next() again resumes.

In the below code for the above generator function, mentioning *done* tells whether originally it's completed or not. Since it says *false* that means it was not fully done. it actually had 
```javascript
console.log(generator.next().value); // Output: 1         { value: 1, done: false }
console.log(generator.next().value); // Output: 2         { value: 2, done: false }
console.log(generator.next().done);  // Output: false     { value: 3, done: false }
console.log(generator.next().value); // Output: 4         { value: 4, done: true }
console.log(generator.next().value); // Output: undefined { value: undefined, done: true }
```

<br>

## What is the purpose of **export** keyword?

The purpose of the export keyword in JavaScript modules is to ***mark a variable, function, or class as publicly accessible from outside*** the module. By using the export keyword, you indicate that the exported item can be used by other modules that import it.

When you use the export keyword before a declaration, it exposes that declaration to be imported and used in other modules. 

<br>

## What is memory leak in Javascript?

A memory leak in JavaScript occurs when a variable, object, or data structure is not properly de-allocated from memory even though it is no longer needed or reachable by the program. 

This can result in a gradual accumulation of unreferenced objects or data in memory, causing the overall memory usage of the program to increase over time. 

Common causes of memory leaks in JavaScript include:

***Unintentional global variables***: Variables declared in the global scope can persist in memory even if they are no longer needed, preventing them from being garbage collected.

***Closures***: Closures, which capture references to outer variables, can inadvertently keep those variables alive longer than necessary, leading to memory leaks if not handled properly.

***Event listeners and callbacks***: Registering event listeners or callbacks without properly removing them when they are no longer needed can result in memory leaks, as the associated objects or functions continue to be referenced and not garbage collected.

***Circular references***: When two or more objects reference each other in a circular manner, they may remain in memory even if they are no longer reachable from the rest of the program, causing a memory leak.

To avoid memory leaks in JavaScript, it is important to be mindful of 
- variable scope.
- properly manage references.
- remove event listeners and callbacks when they are no longer needed.
- handle circular references appropriately.

<br>



## Is javascript a statically typed or a dynamically typed language?

JavaScript is a dynamically typed language. In a dynamically typed language, the type of a variable is checked during run-time in contrast to a statically typed language, where the type of a variable is checked during compile-time.

Since javascript is a loosely(dynamically) typed language, variables in JS are not associated with any type. A variable can hold the value of any data type.

For example, a variable that is assigned a number type can be converted to a string type.

![Static vs Dynamic Typing](https://d3n0h9tb65y8q.cloudfront.net/public_assets/assets/000/003/407/original/static_vs_dynamic.png?1654852333)


*Refer Miscellaneous for RunTime and CompileTime*


## *What is NaN property in JavaScript?*

*NaN* property represents the “Not-a-Number” value. It indicates a value that is not a legal number.

*typeof* of NaN will return a Number.

To check if a value is NaN, we use the isNaN() function,

Note- *isNaN() function converts the given value to a Number type, and then equates to NaN.*

isNaN("Hello")  // Returns `true`
isNaN(345)   // Returns `false`
isNaN('1')  // Returns `false`, since '1' is converted to Number type which results in 0 ( a number) 
isNaN(true) // Returns `false`, since true converted to Number type results in 1 ( a number)
isNaN(false) // Returns `false`
isNaN(undefined) // Returns `true`



## What is an Immediately Invoked Function (IIFE) in JavaScript?

It is a JavaScript design pattern that involves creating a function and immediately executing it. 

```javascript
function(){ 
  // Do something;
})();
```
To understand IIFE, we need to understand the two sets of parentheses that are added while creating an IIFE :

The first set of parenthesis:

```javascript
(function (){
   //Do something;
})
```
While executing javascript code, whenever the compiler sees the word *“function”*, it assumes that we are declaring a function in the code. Therefore, if we do not use the first set of parentheses, the compiler throws an error because it thinks we are declaring a function, and by the syntax of declaring a function, a function should always have a name.

```javascript
function() {
  //Do something;
};
```
// Compiler gives an error since the syntax of declaring a function is wrong in the code above.
To remove this error, we add the first set of parenthesis that tells the compiler that the function is not a function declaration, instead, it’s a function expression.

The second set of parenthesis:

```javascript 
(function (){
  //Do something;
})();
```
From the definition of an IIFE, we know that our code should run as soon as it is defined. A function runs only when it is invoked. If we do not invoke the function, the function declaration is returned:

```javascript
(function (){
  // Do something;
})
// Returns the function declaration

```

Therefore to invoke the function, we use the second set of parenthesis

***Advantages of using IIFE***

- *Encapsulation*: The variables and functions defined within an IIFE are not accessible from the outside scope. They are encapsulated within the function, which helps prevent variable name clashes and keeps the global namespace clean.

- *Privacy*: Since the variables and functions within an IIFE are not accessible from the outside, it provides a way to create private variables and functions. This can be useful for creating modules or libraries where you want to expose only specific functionality.

- *Avoiding global scope pollution*: By enclosing your code within an IIFE, you prevent polluting the global scope with variables and functions. This is particularly important when working on larger projects or when using third-party libraries to avoid conflicts.

- *Controlled execution*: The code within an IIFE executes immediately after its definition. This can be useful for initializing variables, setting up configurations, or executing a block of code that needs to run once.

- *Avoiding naming collisions*: Since the variables and functions within an IIFE have their own scope, you can use variable and function names freely without worrying about conflicting with other code.

Overall, IIFEs are commonly used in JavaScript to create private scopes, avoid global namespace pollution, and provide encapsulation for modular code.

However, there are some cases where using an IIFE may not be necessary or appropriate:

- *ES Modules*: With the introduction of ES modules in modern JavaScript, you have the option to use import and export statements to achieve encapsulation and modular code. If you are working with a modern JavaScript environment that supports modules, you may consider using modules instead of relying solely on IIFEs.

- *Event handlers* 

- *Global initialization*: If you need to perform global initialization tasks, such as setting up configuration variables or initializing libraries, an IIFE might not be necessary.





## What is non-blocking vs blocking?

- In computer systems, "blocking" and "non-blocking" are terms used to describe how a program or system responds to requests or events. **Blocking methods execute synchronously and non-blocking methods execute asynchronously**.
-  A blocking operation is one that stops the program from continuing until it has completed. During a blocking operation, the program will not respond to other requests or events. For example, if a program needs to read data from a file, it might block until the entire file is read. During this time, the program cannot perform any other tasks.
    - Example =>   
    ```javascript
      const fs = require("fs");
      const data = fs.readFileSync("/file.md"); // blocks here until file is read
      console.log(data);
      moreWork(); // will run after console.log

-  a non-blocking operation is one that allows the program to continue executing even if the requested operation is not yet complete. If the operation cannot be completed immediately, the program can move on to perform other tasks or wait for the operation to complete at a later time. Non-blocking operations are typically used in applications that require high performance and responsiveness, such as real-time systems or web servers.
    - Example =>  
     ```javascript  
      const fs = require("fs");
      fs.readFile("/file.md", (err, data) => {
         if (err) throw err;
            console.log(data);
            });
      moreWork(); // will run before console.log



## What is common.js? how is it different from es modules?
- CommonJS (or CJS) is a module system used in Node.js for organizing and sharing code between files. It was created before the introduction of ES Modules
- In CommonJS, modules are loaded synchronously, which means that the module's code is executed as soon as it is loaded. CommonJS modules use the require() function to import modules and the module.exports object to export functionality from a module.
- ES Modules (or ES6 Modules) is a module system introduced in ECMAScript 6 (ES6) and is supported in modern browsers and Node.js versions. ES Modules use a static import/export syntax to import and export functionality between modules.ES Modules are loaded asynchronously, which means that the module's code is executed only when it is needed. This can lead to better performance in some cases, as modules are loaded and executed only when they are needed.
- One of the main differences between CommonJS and ES Modules is how they handle exports. In CommonJS, a module can export a single value or a collection of values through the module.exports object. In contrast, ES Modules export individual values using the export keyword.
- Another difference is that CommonJS modules are evaluated synchronously and loaded dynamically, while ES Modules are evaluated asynchronously and loaded statically at compile-time.


## What is event Delegation in Javascript?

Event Delegation is a pattern based upon the concept of ***Event Bubbling***. It is an event-handling pattern that allows you to handle events at a higher level in the DOM tree other than the level where the event was first received.
By default, events triggered on an element propagate up the DOM tree to the element's parent, its ancestors, and on up until the root element (html).

```javascript
<div>
  <span>
    <button>Click Me!</button>
  </span>
</div>
```

Here we have a *div* which is a parent of a *span* which in turn is a parent of the *button* element.

Due to event bubbling, when the button receives an event, say click, that event bubbles up the tree, so span and div will respectively receive the event also.


## How Does Event Delegation Work?
With event delegation, instead of handling the click event on the button, you can handle it on the div.

The idea is that you "delegate" the handling of an event to a different element (in this case, the div, which is a parent element) instead of the actual element (the button) that received the event.

Here's what it means in code:

```javascript
const div = document.getElementsByTagName("div")[0]

div.addEventListener("click", (event) => {
  if(event.target.tagName === 'BUTTON') {
    console.log("button was clicked")
  }
})
```


The event object has a target property which contains information about the element that actually received the event. On target.tagName, we get the name of the tag for the element, and we check if it's BUTTON.

With this code, when you click the button, the event bubbles up to the div which handles the event.

***Benefits of Event Delegation***
Event Delegation is a useful pattern that allows you to write cleaner code, and create fewer event listeners with similar logic.

What do I mean by this? Look at this code:

```javascript
<div>
  <button>Button 1</button>
  <button>Button 2</button>
  <button>Button 3</button>
</div>
```
Here we have 3 buttons. Let's say we wanted to handle a click event on each button, such that when it is clicked, the button's text is logged to the console. We can implement that like this:

```javascript
const buttons = document.querySelectorAll('button')

buttons.forEach(button => {
  button.addEventListener("click", (event) => {
    console.log(event.target.innerText)
  })
})
```

I'm using *querySelectorAll* here as it returns a NodeList which I can use the *forEach* method for. getElementsByTagName returns an HTMLCollection which doesn't have the *forEach* method.

When you click on the first button, you have "Button 1" logged on the console. For the second button, "Button 2" is logged, and for the third button, "Button 3" is logged.

Although this works as we want, we have created three event listeners for the three buttons.

Since the click event on these buttons propagates upward in the DOM tree, we can use a common parent or ancestor that they have to handle the event. In this case, we delegate a common parent that they share to handle the logic we want.

Here's how:

```javascript
const div = document.querySelector('div')

div.addEventListener("click", (event) => {
  if(event.target.tagName === 'BUTTON') {
    console.log(event.target.innerText)
  }
})
```


Now, we have just one event listener, but the same logic: when you click the first button, "Button 1" is logged to the console, and the same thing for the other buttons.

Even if we add an extra button like this:

```javascript
<div>
  <button>Button 1</button>
  <button>Button 2</button>
  <button>Button 3</button>
  <button>Button 4</button>
</div>
```
We won't have to change the JavaScript code as this new button also shares the div parent (which we delegated for the event handling) with the other buttons.

Wrapping Up
With event delegation, you create fewer event listeners and perform similar events-based logic in one place. This makes it easier for you to add and remove elements without having to add new or remove existing event listeners.

Event delegation is possible because of event propagation in the DOM, where the event a child element receives is also passed to the child's parent and ancestors.

SOURCE: https://www.freecodecamp.org/news/event-delegation-javascript/