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




