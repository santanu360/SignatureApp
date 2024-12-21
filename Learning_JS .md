
# JavaScript Variable Declarations

## Declaring Variables Using `var`
```javascript
var name = "John";
var age = 30;
var isStudent = true;
```


## Declaring Variables Using `let`
```javascript
let city = "New York";
let score = 85;
let isGraduated = false;
```

## Declaring Variables Using `const`
```javascript
const country = "USA";
const PI = 3.14159;
const isEmployed = true;
```

## Variable Reassignment
```javascript
name = "Jane";
age = 25;
city = "Los Angeles";
score = 90;
```

> **Note:** Trying to reassign a `const` variable will cause an error.
```javascript
// country = "Canada"; // Uncommenting this line will cause an error
```

## Console Output
```javascript
console.log(name); // Output: Jane
console.log(age); // Output: 25
console.log(isStudent); // Output: true
console.log(city); // Output: Los Angeles
console.log(score); // Output: 90
console.log(isGraduated); // Output: false
console.log(country); // Output: USA
console.log(PI); // Output: 3.14159
console.log(isEmployed); // Output: true
```

## Most Asked **INTERVIEW Questions About Variables in JavaScript

### 1. What is the difference between `var`, `let`, and `const`?
- **`var`**: Function-scoped or globally-scoped, can be redeclared and updated.
- **`let`**: Block-scoped, can be updated but not redeclared within the same scope.
- **`const`**: Block-scoped, cannot be updated or redeclared, must be initialized during declaration.

### 2. Can you reassign a value to a variable declared with `const`?
No, variables declared with `const` cannot be reassigned. They are read-only after the initial assignment.

### 3. What happens if you try to use a variable before declaring it?
- **`var`**: The variable is hoisted and initialized with `undefined`.
- **`let`** and **`const`**: Accessing the variable before declaration results in a `ReferenceError`.

### 4. What is variable hoisting?

In JavaScript, variable hoisting refers to the behavior where variable declarations are moved to the top of their containing scope during the compilation phase. However, the way `var`, `let`, and `const` are hoisted differs, leading to different behaviors.

### `var` Hoisting
When you declare a variable using `var`, the declaration is hoisted to the top of its scope, but the initialization remains in place. This means the variable is defined but not initialized until the code execution reaches the line where the variable is assigned a value. If you try to access the variable before its initialization, it will return `undefined`.

Example:
```javascript
console.log(hoistedVar); // Output: undefined
var hoistedVar = "I am hoisted";
```
Here, 

hoistedVar

 is hoisted and declared at the top, but its value is `undefined` until the assignment.

### `let` and `const` Hoisting
Variables declared with `let` and `const` are also hoisted, but they are not initialized. They are placed in a "temporal dead zone" (TDZ) from the start of the block until the declaration is encountered. Accessing them before the declaration results in a `ReferenceError`.

Example with `let`:
```javascript
try {
  console.log(hoistedLet); // ReferenceError
} catch (e) {
  console.error(e);
}
let hoistedLet = "I am not hoisted";
```
Example with `const`:
```javascript
try {
  console.log(hoistedConst); // ReferenceError
} catch (e) {
  console.error(e);
}
const hoistedConst = "I am not hoisted";
```
In both cases, accessing 

hoistedLet

 or 

hoistedConst

 before their declarations results in a `ReferenceError` because they are in the TDZ.

### Summary
- `var`: Hoisted and initialized to `undefined`.
- `let` and `const`: Hoisted but not initialized, leading to a `ReferenceError` if accessed before declaration.



### 5. Can you declare a variable without initializing it?
Yes, you can declare a variable without initializing it. The variable will be `undefined` until it is assigned a value.
```javascript
let uninitializedVar;
console.log(uninitializedVar); // Output: undefined
```

### IMPORTANT ****

## Temporal Dead Zone (TDZ) in JavaScript

The Temporal Dead Zone (TDZ) is a behavior in JavaScript that occurs when using `let` and `const` declarations. It refers to the time between entering a block and the point where the variable is declared. During this period, the variable cannot be accessed and any attempt to do so will result in a `ReferenceError`.

#### Key Points:
1. **Scope**: The TDZ starts from the beginning of the block until the variable is declared.
2. **Access**: Accessing the variable within the TDZ results in a `ReferenceError`.
3. **Initialization**: Variables declared with `let` and `const` are not initialized until their declaration is evaluated.

#### Example:
```javascript
{
  // TDZ starts
  try {
    console.log(myVar); // ReferenceError
  } catch (e) {
    console.error(e);
  }
  
  let myVar; // TDZ ends
  myVar = 10;
  console.log(myVar); // Output: 10
}
```

In the example above, `myVar` is in the TDZ from the start of the block until the `let` declaration is encountered.

### Why TDZ Exists:
The TDZ helps catch errors and bugs by preventing the use of variables before they are declared. This ensures that variables are not used in an uninitialized state.


## Type Coercion in JavaScript

Type coercion is the process of converting a value from one type to another (such as a string to a number, or an object to a boolean) in JavaScript. This can happen implicitly (automatically by JavaScript) or explicitly (manually by the developer).

### Implicit Coercion
Implicit coercion occurs when JavaScript automatically converts types during operations. This can sometimes lead to unexpected results.

#### Example:
```javascript
console.log('5' + 3); // Output: '53' (string concatenation)
console.log('5' - 3); // Output: 2 (string '5' is converted to number 5)
console.log(true + 1); // Output: 2 (true is converted to number 1)
console.log(false + 1); // Output: 1 (false is converted to number 0)
```

### Explicit Coercion
Explicit coercion is when you manually convert a value from one type to another using functions or operators.

#### Example:
```javascript
console.log(Number('5')); // Output: 5 (string '5' is converted to number 5)
console.log(String(123)); // Output: '123' (number 123 is converted to string '123')
console.log(Boolean(0)); // Output: false (number 0 is converted to boolean false)
console.log(Boolean(1)); // Output: true (number 1 is converted to boolean true)
```

### Important Concepts

#### Truthy and Falsy Values
In JavaScript, certain values are considered "truthy" or "falsy" when evaluated in a boolean context.

- **Falsy values**: `false`, `0`, `-0`, `0n`, `""`, `null`, `undefined`, `NaN`
- **Truthy values**: All values that are not falsy

#### Example:
```javascript
if (0) {
  console.log('This will not run');
} else {
  console.log('0 is falsy'); // Output: 0 is falsy
}

if ('hello') {
  console.log('This will run'); // Output: This will run
}
```




