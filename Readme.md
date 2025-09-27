# JavaScript Functions and Condions

## Learning Goals

- [ ] Review funcitons in Javascript.
- [ ] Explain hoisting for function declarations vs functions saved to variables.
- [ ] Save functions to variables using function expressions.
- [ ] Write arrow functions.
- [ ] Define and call functions with parameters and arguments.
- [ ] Return values from functions and use those returns to build a calculator.

## Functions in JavaScript

A function is a reusable block of code. You define it once and call it many times. They work similar to functions in other languages but have a few unique properties.

```
  //Declaring a function with the function keyword
  function foo() {}

  // Saving a function to a variable is called a function expression
  const boo = function () {}

  // Arrow functions
   const foo = () => {}

```

### Hoisting

- Function declarations with the function keyword are [hoisted](https://www.youtube.com/watch?v=EvfRXyKa_GI). Which means you can actually call the function before it's defined.

- Functions saved to variables and arrow functions are not hoisted the same way.

## Console.log

Console.log is a way to print values to the console.  
This is a great debugging tool that helps you check what your code is doing at different points in a program.

```
console.log("hello world")
```

## Parameters and Arguments

- **Parameters** are the named variables in the function definition.
- **Arguments** are the values you pass in when calling the function.
- You can give default values to parameters.

```
  function foo(num){
    console.log(num)
  }

  foo(10) // 10

  // Default paramaters
  function boo(num = 5) {
    console.log(num);
  }
  boo() // 5
```

## Return Values

`return` provides an output for the function and stops the functions execution. This value can be saved into a variable for access later.

```
  function foo(num){
    return num*num
  }
  foo(10) // 100

  function boo(name){
    return "Hello "+name
  }

  let greeting = boo("rose")
  console.log(greeting) // Hello rose
```

---

## Arrow Functions

Arrow functions are a compact way to write functions.  
They can be written as one-liners that return a value without using the `return` keyword, or as multi-line functions with an explicit `return`.

```
  const foo = num => num*num
  foo(2) // 4
```

### Conditions

JavaScript uses **if / else if / else** statements to run different code depending on logical conditions.  
If \_**\_ is true, do this; else, do \_\_**.

Imagine being at a crossroads.  
A condition asks if something is true.  
For example, if you are hungry, you’ll go down the road to your favorite café; otherwise, you’ll head down the road home.
That's a bit how Conditionals work.

```
              [Start]
                 |
  [no] <--[Condition True?]--> [yes]
   |                             |
[Do Nothing]             [Perform Action]
```

**Comparison and logical operators:**
These are logical operations that are paired with your if/else statments. 

- `==` – equal to (1 == "1" is true)
- `===` – strict equal to (1 == "1" is false)
- `!=` – not equal to
- `!==` – strict not equal to
- `<` – less than
- `>` – greater than
- `<=` – less than or equal to
- `>=` – greater than or equal to
- `&&` – logical AND (both conditions must be true)
- `||` – logical OR (at least one condition must be true)
- `!` – logical NOT (reverses the truthiness of a condition)

```
  if (condition) {
  }

  else if (anotherCondition) {
  }

  else {
  }

  const num1 = 1;
  const num2 = 2;

  if (num1 + num2 === 3) {
    console.log("Number is 3");

  } else if (num1 + num2 > 3) {
    console.log("Number is greater than 3");

  } else {
    console.log("Number is less than 3");

  };
```

Conditional statements can also be written in shorthand when the action fits on a single line.

```
// Single-line if statement
// If the name is "rose", immediately return the string "hello rose"

  let name = "rose"
  if (name === "rose") return "hello rose"

// Logical AND (&&) shorthand
// If darkMode is true, this will print "Dark Mode On" to the console

  let darkMode = true
  darkMode && console.log("Dark Mode On")

// Ternary operator
// If age is greater than 21, print the first message; otherwise, print the second message

  let age = 21
  age > 21 ? console.log("You can get into the club") : console.log("Sorry you're too young")


```

## Lab Deliverables

### 1) Write four calculator operations

Create `add`, `subtract`, `multiply`, and `divide`.

- Create a file called **calculator.js** and enter your code for this assignment into it.
- `add` must be a function declaration to demonstrate hoisting.
- `subtract` must be a function expression saved to a variable.
- `multiply` must be an arrow function.
- `divide` must check for divide by zero and return the string `"Cannot divide by zero"` if the second number is 0.

---

<details>
<summary>Click here to view a sample solution</summary>

```

console.log(add(2, 3)); // 5
// Function declaration (hoisted)
function add(a, b) {
return a + b;
}

// Function expression saved to a variable
const subtract = function (a, b) {
return a - b;
};

// Arrow function
const multiply = (a, b) => a * b;

// Arrow function with a guard
const divide = (a, b) => {
  if (b === 0){
    return "Cannot divide by zero"
  }
return a / b;
}

console.log(subtract(7, 4)); // 3
console.log(multiply(3, 5)); // 15
console.log(divide(10, 0)); // "Cannot divide by zero"

```

</details>

### 2) Build a calculate

Create a function `calculate(a, b, operation)`

- `operation` can be `"+"`, `"-"`, `"*"`, or `"/"`.
- Use a map of operations where the values are the functions you created, then call the correct function.

---

<details>
<summary>Click here to view a sample solution</summary>

```

// Map of operations to functions
function calculate(a, op, b) {
  if (op === "+") {
    return add(a, b);

  } else if (op === "-") {
    return subtract(a, b);

  } else if (op === "\*") {
    return multiply(a, b);

  } else if (op === "/") {
    return divide(a, b);

  } else {
    return "Unknown operator";

  };
};

console.log(calculate(10, "+", 5)); // 15
console.log(calculate(10, "/", 2)); // 5
console.log(calculate(1,2,%)) //"Unknown operator"

```

</details>

## Reference Links

- [MDN: Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
- [MDN: Arrow function expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)

## Submission Instructions

1. Put your code in a single file called `calculator.js`.
2. Push your code to GitHub.
3. Submit your repository URL.
