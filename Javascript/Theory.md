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







