# JavaScript Functions

## Types of Functions

### 1. Function Declaration
A function declaration defines a named function. It is hoisted, meaning it can be called before it is defined.

```javascript
function greet() {
  console.log("Hello, World!");
}

greet(); // Output: Hello, World!
```

### 2. Function Expression
A function expression defines a function inside an expression. It is not hoisted.

```javascript
const greet = function() {
  console.log("Hello, World!");
};

greet(); // Output: Hello, World!
```

### 3. Arrow Function
Arrow functions provide a shorter syntax and do not have their own `this` context.

```javascript
const greet = () => {
  console.log("Hello, World!");
};

greet(); // Output: Hello, World!
```

### 4. Anonymous Function
An anonymous function is a function without a name. It is often used as an argument to other functions.

```javascript
setTimeout(function() {
  console.log("Hello, World!");
}, 1000);
```

### 5. Immediately Invoked Function Expression (IIFE)
An IIFE is a function that runs as soon as it is defined.

```javascript
(function() {
  console.log("Hello, World!");
})();
```

## Important Points

- **Hoisting**: Function declarations are hoisted, meaning they can be called before they are defined. Function expressions and arrow functions are not hoisted.
- **`this` Context**: Arrow functions do not have their own `this` context; they inherit `this` from the parent scope.
- **Parameters and Arguments**: Functions can take parameters and arguments. Default parameters can be set.
- **Return Value**: Functions can return a value using the `return` statement.
- **First-Class Functions**: In JavaScript, functions are first-class citizens, meaning they can be assigned to variables, passed as arguments, and returned from other functions.

## Higher-Order Functions

Higher-order functions are functions that operate on other functions, either by taking them as arguments or by returning them.

### Example of Higher-Order Function

```javascript
function higherOrder(fn) {
  return function(x) {
    return fn(x);
  };
}

const double = higherOrder(function(x) {
  return x * 2;
});

console.log(double(5)); // Output: 10
```

## `map` Function

The `map` function creates a new array populated with the results of calling a provided function on every element in the calling array.

### Example of `map`

```javascript
const numbers = [1, 2, 3, 4];
const doubled = numbers.map(function(num) {
  return num * 2;
});

console.log(doubled); // Output: [2, 4, 6, 8]
```

## Custom Mapper

A custom mapper function can be created to transform array elements.

### Example of Custom Mapper

```javascript
function customMap(arr, fn) {
  const result = [];
  for (let i = 0; i < arr.length; i++) {
    result.push(fn(arr[i]));
  }
  return result;
}

const numbers = [1, 2, 3, 4];
const doubled = customMap(numbers, function(num) {
  return num * 2;
});

console.log(doubled); // Output: [2, 4, 6, 8]
```

## `filter` Function

The `filter` function creates a new array with all elements that pass the test implemented by the provided function.

### Example of `filter`

```javascript
const numbers = [1, 2, 3, 4];
const evenNumbers = numbers.filter(function(num) {
  return num % 2 === 0;
});

console.log(evenNumbers); // Output: [2, 4]
```

## `reduce` Function

The `reduce` function executes a reducer function on each element of the array, resulting in a single output value.

### Example of `reduce`

```javascript
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce(function(accumulator, currentValue) {
  return accumulator + currentValue;
}, 0);

console.log(sum); // Output: 10
```
## Callback Functions

A callback function is a function that is passed as an argument to another function and is executed after some operation has been completed. Callbacks are used to handle asynchronous operations in JavaScript.

### Example of Callback Function

```javascript
function fetchData(callback) {
  setTimeout(function() {
    const data = { name: "John", age: 30 };
    callback(data);
  }, 2000);
}

function displayData(data) {
  console.log(`Name: ${data.name}, Age: ${data.age}`);
}

fetchData(displayData); // Output after 2 seconds: Name: John, Age: 30
```

## Important Points

- **Asynchronous Operations**: Callbacks are commonly used to handle asynchronous operations such as network requests, file reading, and timers.
- **Error Handling**: Callbacks can also be used for error handling by passing an error object as the first argument.
- **Nested Callbacks**: Excessive use of callbacks can lead to "callback hell," making the code difficult to read and maintain. Promises and async/await can help mitigate this issue.
- **Higher-Order Functions**: Functions that accept callbacks are higher-order functions.

### Example of Error Handling with Callback

```javascript
function fetchData(callback) {
  setTimeout(function() {
    const error = false;
    if (error) {
      callback("Error fetching data", null);
    } else {
      const data = { name: "John", age: 30 };
      callback(null, data);
    }
  }, 2000);
}

function displayData(error, data) {
  if (error) {
    console.log(error);
  } else {
    console.log(`Name: ${data.name}, Age: ${data.age}`);
  }
}

fetchData(displayData); // Output after 2 seconds: Name: John, Age: 30
```

## Callback Hell

Callback hell, also known as the "Pyramid of Doom," occurs when multiple nested callbacks make the code difficult to read and maintain. This often happens in asynchronous programming when one callback depends on the result of another callback, leading to deeply nested code.
Callback hell is basically **Readability** Problem.

## Example of Callback Hell

``` javascript

function firstFunction(callback) {
  setTimeout(function() {
    console.log("First function completed");
    callback();
  }, 1000);
}

function secondFunction(callback) {
  setTimeout(function() {
    console.log("Second function completed");
    callback();
  }, 1000);
}

function thirdFunction(callback) {
  setTimeout(function() {
    console.log("Third function completed");
    callback();
  }, 1000);
}

// Nested callbacks leading to callback hell
firstFunction(function() {
  secondFunction(function() {
    thirdFunction(function() {
      console.log("All functions completed");
    });
  });
});
```

### Mitigating Callback Hell

To avoid callback hell, you can use Promises or async/await, which provide a more readable and maintainable way to handle asynchronous operations.

#### Using Promises

```javascript
function firstFunction() {
  return new Promise(function(resolve) {
    setTimeout(function() {
      console.log("First function completed");
      resolve();
    }, 1000);
  });
}

function secondFunction() {
  return new Promise(function(resolve) {
    setTimeout(function() {
      console.log("Second function completed");
      resolve();
    }, 1000);
  });
}

function thirdFunction() {
  return new Promise(functi
      console.log("Third function completed");
      resolve();
    }, 1000);
  });
}

// Chaining promises to avoid callback hell
firstFunction()
  .then(secondFunction)
  .then(thirdFunction)
  .then(function() {
    console.log("All functions completed");
  });
```

#### Using async/await

```javascript

function firstFunction() {
  return new Promise(function(resolve) {
    setTimeout(function() {
      console.log("First function completed");
      resolve();
    }, 1000);
  });
}

function secondFunction() {
  return new Promise(function(resolve) {
    setTimeout(function() {
      console.log("Second function completed");
      resolve();
    }, 1000);
  });
}

function thirdFunction() {
  return new Promise(function(resolve) {
    setTimeout(function() {
      console.log("Third function completed");
      resolve();
    }, 1000);
  });
}

async function runFunctions() {
  await firstFunction();
  await secondFunction();
  await thirdFunction();
  console.log("All functions completed");
}

// Using async/await to avoid callback hell

```
```javascript
runFunctions();
on(resolve) {
    setTimeout(function() {
      console.log("Third function completed");
      resolve();
        }, 1000);
      });
    }

    // Chaining promises to avoid callback hell
    firstFunction()
      .then(secondFunction)
      .then(thirdFunction)
      .then(function() {
        console.log("All functions completed");
      });

  ```

  ## Using async/await

    ```javascript
    function firstFunction() {
      return new Promise(function(resolve) {
        setTimeout(function() {
      console.log("First function completed");
      resolve();
        }, 1000);
      });
    }

    function secondFunction() {
      return new Promise(function(resolve) {
        setTimeout(function() {
      console.log("Second function completed");
      resolve();
        }, 1000);
      });
    }

    function thirdFunction() {
      return new Promise(function(resolve) {
        setTimeout(function() {
      console.log("Third function completed");
      resolve();
        }, 1000);
      });
    }

    async function runFunctions() {
      await firstFunction();
      await secondFunction();
      await thirdFunction();
      console.log("All functions completed");
    }

    // Using async/await to avoid callback hell
    runFunctions();
  ```
  ## Inversion of Control

    Inversion of control is an issue that arises when you pass a callback function to another function, giving up control over when and how the callback is executed. This can lead to unexpected behavior and make the code harder to understand and maintain.

  ## Example of Inversion of Control

    ```javascript
    function fetchData(callback) {
      setTimeout(function() {
        const data = { name: "John", age: 30 };
        callback(data);
      }, 2000);
    }

    function processData(data) {
      console.log(`Processing data: Name: ${data.name}, Age: ${data.age}`);
    }

    // Passing processData as a callback to fetchData
    fetchData(processData);
    ```

    In this example, the `fetchData` function controls when the `processData` callback is executed. If `fetchData` changes its implementation, it could affect how and when `processData` is called, leading to potential issues.

  ## Mitigating Inversion of Control

    To mitigate inversion of control, you can use Promises or async/await, which provide more control over the flow of asynchronous operations.

  ### Using Promises

    ```javascript
    function fetchData() {
      return new Promise(function(resolve) {
        setTimeout(function() {
          const data = { name: "John", age: 30 };
          resolve(data);
        }, 2000);
      });
    }

    fetchData().then(function(data) {
      console.log(`Processing data: Name: ${data.name}, Age: ${data.age}`);
    });
    ```

  ## Using async/await

    ```javascript
    function fetchData() {
      return new Promise(function(resolve) {
        setTimeout(function() {
          const data = { name: "John", age: 30 };
          resolve(data);
        }, 2000);
      });
    }

    async function processData() {
      const data = await fetchData();
      console.log(`Processing data: Name: ${data.name}, Age: ${data.age}`);
    }

    processData();
   ```