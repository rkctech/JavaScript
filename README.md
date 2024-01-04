# JavaScript Variable Declaration and Modification
```javascript
// Using const for a constant value (cannot be reassigned)
const accountId = 144553;

// Using let for variables that may be reassigned
let accountEmail = "hitesh@google.com";
let accountPassword = "12345";

// Using var (prefer let or const) - consider avoiding var due to scope issues
var accountCity = "Jaipur";

// Declaring a variable without assigning a value (undefined by default)
let accountState;

// Chained Assignment
// Multiple variables can be assigned the same value in a single line.

let num1, num2, num3;
num1 = num2 = num3 = 2 + 2; // All three variables become 4

// Uncommenting the line below will result in an error because you cannot reassign a constant
// accountId = 2;

// Modifying the values of the variables
accountEmail = "hc@hc.com";
accountPassword = "21212121";
accountCity = "Bengaluru";

// Logging the value of accountId
console.log(accountId);

// Displaying the values of the variables in a table format
console.table([accountId, accountEmail, accountPassword, accountCity, accountState]);
```

**Output:**
```plaintext
144553
┌────────────────┬────────────────────┐
│ (index)        │      Values        │
├────────────────┼────────────────────┤
│   accountId    │       144553       │
│ accountEmail   │ 'hc@hc.com'        │
│ accountPassword│    '21212121'      │
│  accountCity   │   'Bengaluru'      │
│ accountState   │       undefined    │
└────────────────┴────────────────────┘
```
#  JavaScript Data Types and Variable Declarations
```javascript
// Number: Represents numeric values, maximum safe integer is 2 to the power of 53
let myNumber = 42;
console.log(typeof myNumber); // Output: number

// BigInt: Represents integers of arbitrary precision
let myBigInt = 9007199254740991n;
console.log(typeof myBigInt); // Output: bigint

// String: Represents text, can be enclosed in double ("") or single ('') quotes
let myString = "Hello, World!";
console.log(typeof myString); // Output: string

// Boolean: Represents true or false values
let isTrue = true;
console.log(typeof isTrue); // Output: boolean

// Null: Represents a deliberate absence of any object value
let nullValue = null;
console.log(typeof nullValue); // Output: object (known quirk in JavaScript)

// Undefined: Represents a variable or object property that has not been assigned a value
let undefinedVariable;
console.log(typeof undefinedVariable); // Output: undefined

// Symbol: Represents a unique and immutable data type, used to create unique identifiers
let mySymbol = Symbol("unique");
console.log(typeof mySymbol); // Output: symbol
```
# Understanding null and undefined in JavaScript

### 1. `null`:
- **Definition:** `null` is a special value representing the intentional absence of any object value.
- **Use Cases:**
  - Used when a variable or property is explicitly meant to have no value.
  - It is often used as a placeholder to indicate that a certain value is missing or unknown.

**Example:**
```javascript
let myVariable = null;
console.log(myVariable); // Output: null
```

### 2. `undefined`:
- **Definition:** `undefined` is a primitive value automatically assigned to variables that have been declared but not assigned a value.
- **Use Cases:**
  - Represents the absence of a meaningful value.
  - Indicates that a variable or object property has not been initialized or assigned a value.

**Example:**
```javascript
let myVariable;
console.log(myVariable); // Output: undefined
```

**Note:**
- While `null` is a deliberate assignment to indicate a lack of value, `undefined` often represents the default state of variables that haven't been explicitly set.
  
  # JavaScript Type Conversion with Number(), Boolean(), and String() Functions
  The `Number()`, `Boolean()`, and `String()` functions in JavaScript are used for type conversion, allowing you to explicitly convert values from one data type to another. Here's a brief explanation of each:

### 1. `Number()` Function:
- **Purpose:** Converts a value to a number.
- **Usage:**
  ```javascript
  let stringValue = "33";
  let numericValue = Number(stringValue);
  ```
- **Conversion Rules:**
  - Strings containing numeric characters are converted to numbers (e.g., "33" becomes 33).
  - Strings with non-numeric characters or invalid numeric formats result in `NaN`.
  - `null` is converted to `0`.
  - `undefined` is converted to `NaN`.
  - `true` is converted to `1`, and `false` is converted to `0`.

### 2. `Boolean()` Function:
- **Purpose:** Converts a value to a boolean.
- **Usage:**
  ```javascript
  let stringValue = "hitesh";
  let booleanValue = Boolean(stringValue);
  ```
- **Conversion Rules:**
  - Numeric values: `1` is converted to `true`, `0` and `NaN` are converted to `false`.
  - Strings: An empty string `""` is converted to `false`, any non-empty string is converted to `true`.
  - `null`, `undefined`, and `NaN` are converted to `false`.
  - Any other non-boolean value is converted to `true`.

### 3. `String()` Function:
- **Purpose:** Converts a value to a string.
- **Usage:**
  ```javascript
  let numericValue = 33;
  let stringValue = String(numericValue);
  ```
- **Conversion Rule:**
  - Any data type can be converted to a string.
  - The conversion is straightforward, preserving the value but representing it as a string.
 
# JavaScript Operators and Type Coercion

## Unary Minus and Unary Plus
- Unary Minus (`-`) negates a numeric value.
- Unary Plus (`+`) attempts to convert an operand to a number.

```javascript
let value = 3;
let negValue = -value; // negValue becomes -3
let posValue = +value; // posValue becomes 3
```

## Arithmetic Operations
- Basic arithmetic operations include addition (+), subtraction (-), multiplication (*), exponentiation (**), division (/), and modulus (%).

```javascript
let addition = 2 + 2; // 4
let subtraction = 2 - 2; // 0
let multiplication = 2 * 2; // 4
let exponentiation = 2 ** 3; // 8
let division = 2 / 3; // 0.666...
let modulus = 2 % 3; // 2
```

## String Concatenation
- The `+` operator is used for string concatenation, joining two strings together.

```javascript
let str1 = "hello";
let str2 = " hitesh";
let str3 = str1 + str2; // "hello hitesh"
```
## Increment and Assignment
- Post-increment (`x++`) and pre-increment (`++x`) operations.

```javascript
let x = 3;
const y = x++; // x: 4, y: 3

let a = 3;
const b = ++a; // a: 4, b: 4
```

## Comparison Operators
- Comparison operators include greater than (>), greater than or equal to (>=), less than (<), equal to (==), and not equal to (!=).

```javascript
let greaterThan = 2 > 1; // true
let greaterThanOrEqual = 2 >= 1; // true
let lessThan = 2 < 1; // false
let equalTo = 2 == 1; // false
let notEqualTo = 2 != 1; // true

const id = Symbol('123');
const anotherId = Symbol('123');
console.log(id === anotherId);//false

```
## Type Coercion
- JavaScript performs type coercion when comparing values of different types.
- Numeric strings are converted to numbers during comparison.
- `null` is treated as 0 in numeric operations.
- `undefined` becomes `NaN` in numeric operations.
- Boolean values are converted to 1 (`true`) or 0 (`false`) in numeric operations.
- 
  **Explicit Type Coercion:**
  Explicit type coercion involves intentionally converting values from one data type to another using functions or operators provided by the developer,
  providing clear instructions for the conversion process.
  
```javascript
let valueInNumber = Number("33"); // 33
let isLoggedIn = "hitesh";
let booleanIsLoggedIn = Boolean(isLoggedIn); // true
let someNumber = 33;
let stringNumber = String(someNumber); // "33"
```
**Implicit Type Coercion:**
Implicit type coercion, also known as type casting or type conversion, is the automatic conversion of values from one data type to another
by the JavaScript engine without explicit instructions from the developer.

## Numeric and String Concatenation
- Numeric and string concatenation result in string conversion if one operand is a string.

```javascript
let numStrConcat1 = "1" + 2; // "12"
let numStrConcat2 = 1 + "2"; // "12"
let strNumConcat1 = "1" + 2 + 2; // "122"
let numStrConcat3 = 1 + 2 + "2"; // "32"
```

## String Comparison
- Strings are compared based on their Unicode code points.

```javascript
let strComparison1 = "2" > 1; // true
let strComparison2 = "02" > 1; // true
```

## Null and Undefined Comparison

```javascript
let nullComparison1 = null > 0; // false
let nullComparison2 = null == 0; // false ( this is specific case in js)
let nullComparison3 = null >= 0; // true
let nullComparison4 = null <= 0;// true

let undefinedComparison1 = undefined > 0; // false
let undefinedComparison2 = undefined == 0; // false
let undefinedComparison3 = undefined >= 0; // false
let undefinedComparison4 = undefined <= 0; // false

let undefinedComparison1 = undefined > null;   // false
let undefinedComparison2 = undefined == null;  // true ( this is specific case in js)
let undefinedComparison3 = undefined >= null;  // false
let undefinedComparison4 = undefined <= null;  // false

```

## Strict Equality
- Strict equality (`===`) compares both value and type.

```javascript
let strictEquality = "2" === 2; // false
```
# Numeric Operations:

```javascript
const score = 400; 
console.log(score); // Output: 400

const balance = new Number(100); // Declares a Number object with value 100 and logs it
console.log(balance); // Output: [Number: 100]
console.log(typeof(balance.toString())); //string
console.log(balance.toString().length); // 3
console.log(balance.toFixed(1)); // Logs the value with one decimal place //100.0

const otherNumber = 123.8966; 
console.log(otherNumber.toPrecision(4)); // 123.9 // Logs the number in exponential notation with precision 4

const hundreds = 1000000;
console.log(hundreds.toLocaleString('en-IN'));// Logs the number formatted as a locale-specific string
// Output: 10,00,000

// Math Operations:

console.log(Math); // Logs the Math object
/*
Output (partial):
Math {
  E: 2.718281828459045,
  LN10: 2.302585092994046,
  LN2: 0.6931471805599453,
  ...
}
*/

console.log(Math.abs(-4)); // Logs the absolute value
// Output: 4

console.log(Math.round(4.6)); // Logs the rounded value
// Output: 5

console.log(Math.ceil(4.2)); // Logs the ceiling value
// Output: 5

console.log(Math.floor(4.9)); // Logs the floor value
// Output: 4

console.log(Math.min(4, 3, 6, 8)); // Logs the minimum value
// Output: 3

console.log(Math.max(4, 3, 6, 8)); // Logs the maximum value
// Output: 8

console.log(Math.random()); // Logs a random number between 0 and 1
// Output: Random decimal between 0 and 1

console.log((Math.random() * 10) + 1); // Logs a random number between 1 and 10
// Output: Random decimal between 1 and 11

console.log(Math.floor(Math.random() * 10) + 1); // Logs a random integer between 1 and 10
// Output: Random integer between 1 and 10

const min = 10;
const max = 20;
console.log(Math.floor(Math.random() * (max - min + 1)) + min); // Logs a random integer between 10 and 20 (inclusive)
// Output: Random integer between 10 and 20
```
# String Operations:

1. **Concatenation:**
   ```javascript
   var str1 = "Hello";
   var str2 = " World";
   var result = str1 + str2;
   var resultConcat = str1.concat(str2);
   // Result: "Hello World"
  
  Explanation: Concatenation combines two strings into a single string.

2. **String Length:**
   ```javascript
   var str = "Hello";
   var length = str.length;
   // Length: 5
   ```
   Explanation: The `length` property provides the number of characters in a string.

3. **Accessing Characters:**
   ```javascript
   var str = "Hello";
   var firstChar = str[0];
   // First Character: "H"
   ```
   Explanation: Square brackets allow access to individual characters by index.

4. **Substring:**
   ```javascript
   var str = "Hello World";
   var substr = str.substring(0, 5);
   // Substring: "Hello"
   ```
   Explanation: The `substring` method extracts a portion of a string based on indices.

5. **Substring with Slice:**
   ```javascript
   var str = "Hello World";
   var slicedStr = str.slice(0, 5);
   // Sliced Substring: "Hello"
   ```
   Explanation: Similar to `substring`, `slice` extracts a substring with start and end indices.

6. **Searching in a String:**
   ```javascript
   var str = "Hello World";
   var index = str.indexOf("World");
   // Index of "World": 6
   ```
   Explanation: The `indexOf` method finds the starting index of a specified text.

7. **Replacing Substrings:**
   ```javascript
   var str = "Hello World";
   var newStr = str.replace("World", "Universe");
   // Replaced String: "Hello Universe"
   ```
   Explanation: The `replace` method replaces a specified substring with another.

8. **Converting Case:**
   ```javascript
   var str = "Hello World";
   var upper = str.toUpperCase();
   var lower = str.toLowerCase();
   // Uppercase: "HELLO WORLD", Lowercase: "hello world"
   ```
   Explanation: `toUpperCase` and `toLowerCase` change the case of the string.

9. **Trimming Whitespace:**
   ```javascript
   var str = "   Hello World   ";
   var trimmedStr = str.trim();
   // Trimmed String: "Hello World"
   ```
   Explanation: The `trim` method removes leading and trailing whitespaces.

10. **trimStart and trimEnd:**
    ```javascript
    var str = "   Hello World   ";
    var trimmedStart = str.trimStart();
    var trimmedEnd = str.trimEnd();


    // Trimmed Start: "Hello World   ", Trimmed End: "   Hello World"
    ```
    Explanation: These methods remove whitespace from the beginning (left) or end (right) of a string.

11. **Splitting a String:**
    ```javascript
    var str = "Hello,World";
    var array = str.split(",");
    // Array: ["Hello", "World"]
    ```
    Explanation: The `split` method separates a string into an array using a specified delimiter.

12. **charAt:**
    ```javascript
    var str = "Hello";
    var char = str.charAt(0);
    // First Character: "H"
    ```
    Explanation: The `charAt` method returns the character at a specified index.

13. **charCodeAt:**
    ```javascript
    var str = "Hello";
    var unicode = str.charCodeAt(0);
    // Unicode of "H": 72
    ```
    Explanation: The `charCodeAt` method returns the Unicode of the character at a specified index.

14. **startsWith and endsWith:**
    ```javascript
    var str = "Hello World";
    var startsWithHello = str.startsWith("Hello"); // true
    var endsWithWorld = str.endsWith("World"); // true
    ```
    Explanation: `startsWith` and `endsWith` check if a string starts or ends with a specific substring.

15. **includes:**
    ```javascript
    var str = "Hello World";
    var containsHello = str.includes("Hello"); // true
    ```
    Explanation: The `includes` method checks if a string contains a specific substring.

16. **repeat:**
    ```javascript
    var str = "Hello ";
    var repeatedStr = str.repeat(3);
    // Repeated String: "Hello Hello Hello"
    ```
    Explanation: The `repeat` method repeats a string a specified number of times.

17. **String interpolation (Template Literals):**
    ```javascript
    var name = "John";
    var greeting = `Hello, ${name}!`;
    // Interpolated String: "Hello, John!"
    ```
    Explanation: Template literals allow string interpolation with `${}`.

18. **String.fromCharCode:**
    ```javascript
    var str = String.fromCharCode(72, 101, 108, 108, 111);
    // Result: "Hello"
    ```
    Explanation: The `String.fromCharCode` method creates a string from specified Unicode values.

19. **String.fromCodePoint:**
    ```javascript
    var str = String.fromCodePoint(72, 101, 108, 108, 111);
    // Result: "Hello"
    ```
    Explanation: The `String.fromCodePoint` method creates a string from specified Unicode code points.

20. **substr:**
    ```javascript
    var str = "Hello World";
    var substr = str.substr(6, 5);
    // Substring from index 6: "World"
    ```
    Explanation: The `substr` method returns a specified number of characters from a string, starting at a specified index.



# Array Methods in JavaScript

JavaScript provides a variety of built-in methods to manipulate arrays. Below are explanations for some commonly used array methods:

## `.push()`

The `.push()` method adds one or more elements to the end of an array and returns the new length of the array.

```javascript
const fruits = ['apple', 'banana'];
fruits.push('orange', 'grape');
// Result: fruits is now ['apple', 'banana', 'orange', 'grape']
```

## `.pop()`

The `.pop()` method removes the last element from an array and returns that element.

```javascript
const fruits = ['apple', 'banana', 'orange'];
const removedFruit = fruits.pop();
// Result: removedFruit is 'orange', fruits is now ['apple', 'banana']
```

## `.unshift()`

The `.unshift()` method adds one or more elements to the beginning of an array and returns the new length of the array.

```javascript
const fruits = ['banana', 'orange'];
fruits.unshift('apple', 'grape');
// Result: fruits is now ['apple', 'grape', 'banana', 'orange']
```

## `.shift()`

The `.shift()` method removes the first element from an array and returns that element.

```javascript
const fruits = ['apple', 'grape', 'banana'];
const removedFruit = fruits.shift();
// Result: removedFruit is 'apple', fruits is now ['grape', 'banana']
```

## `.includes()`

The `.includes()` method checks if an array includes a certain element and returns `true` or `false`.

```javascript
const fruits = ['apple', 'banana', 'orange'];
const hasBanana = fruits.includes('banana');
// Result: hasBanana is true
```

## `.indexOf()`

The `.indexOf()` method returns the first index at which a given element can be found in the array, or -1 if it is not present.

```javascript
const fruits = ['apple', 'banana', 'orange'];
const bananaIndex = fruits.indexOf('banana');
// Result: bananaIndex is 1
```

## `.join()`

The `.join()` method creates and returns a new string by concatenating all elements in an array, separated by a specified separator.

```javascript
const fruits = ['apple', 'banana', 'orange'];
const joinedString = fruits.join(', ');
// Result: joinedString is 'apple, banana, orange'
```

## `.splice()`

The `.splice()` method changes the contents of an array by removing or replacing existing elements and/or adding new elements in place.

```javascript
const fruits = ['apple', 'banana', 'orange'];
fruits.splice(1, 1, 'grape', 'kiwi');
// Result: fruits is now ['apple', 'grape', 'kiwi', 'orange']
```

## `.slice()`

The `.slice()` method returns a shallow copy of a portion of an array into a new array object.

```javascript
const fruits = ['apple', 'banana', 'orange', 'grape', 'kiwi'];
const slicedFruits = fruits.slice(1, 4);
// Result: slicedFruits is ['banana', 'orange', 'grape']
```
## Array.map():
```javascript
const arr = [1, 2, 3, 4];
const squaredArr = arr.map((num) => {
    return num * num;
});
console.log(squaredArr);
// Output: [1, 4, 9, 16]
```

The `map` method transforms each element of the array by applying the provided function (`(num) => num * num` in this case), resulting in a new array where each element is the square of the original element.

## Array.filter():
```javascript
const arr = [1, 2, 3, 4];
const evenNums = arr.filter((num) => {
    return num % 2 === 0;
});
console.log(evenNums);
// Output: [2, 4]
```

The `filter` method creates a new array containing only the elements that satisfy the provided condition. In this example, it filters out only the even numbers.

## Array.reduce():
```javascript
const arr = [1, 2, 3, 4];
const sum = arr.reduce((acc, num) => {
    return acc + num;
}, 0);
console.log(sum);
// Output: 10
```

The `reduce` method iterates through the array, accumulating the values based on the provided function (`(acc, num) => acc + num` in this case). It results in the sum of all elements in the array. The initial value is set to 0 (`0` in this case).

# Exploring JavaScript Looping Constructs

## For-In Loop:
```javascript
for (let key in object) {
    // Code block to be executed
}
```
Example:
```javascript
const myArray = [1, 2, 3, 4];

`for...in` is a loop in JavaScript designed for object iteration and should be avoided for arrays due to potential unexpected behavior. Instead, use `for...of` or array methods like `forEach` for safe and predictable array iteration.

for (let index in myArray) {
  console.log(index, myArray[index]);
}

```

## For-Of Loop (For Iterables - Arrays, Strings, etc.):
```javascript
for (let item of iterable) {
    // Code block to be executed
}
```
Example:
```javascript
const arr = [1, 2, 3, 4];
for (let num of arr) {
    console.log(num);
}
```

## Array.forEach():
In JavaScript, the `forEach` method is commonly used to iterate over elements in an array. The `forEach` function takes a callback function as an argument, and this callback function can take up to three parameters:

1. **currentValue**: The current element being processed in the array.
2. **index (optional)**: The index of the current element being processed.
3. **array (optional)**: The array `forEach` is being called upon.

Here's an example using all three parameters:

```javascript
const numbers = [1, 2, 3, 4, 5];

numbers.forEach(function(currentValue, index, array) {
  console.log(`Value: ${currentValue}, Index: ${index}, Array: [${array}]`);
});
```

In this example:

- `currentValue` represents the current element in the array during each iteration.
- `index` represents the index of the current element.
- `array` is the array that `forEach` is being called upon.

The output of the above code will be:

```
Value: 1, Index: 0, Array: [1,2,3,4,5]
Value: 2, Index: 1, Array: [1,2,3,4,5]
Value: 3, Index: 2, Array: [1,2,3,4,5]
Value: 4, Index: 3, Array: [1,2,3,4,5]
Value: 5, Index: 4, Array: [1,2,3,4,5]
```

Note: The `index` and `array` parameters are optional, and you can choose to use only the ones you need in your callback function.
## For Loop:
```javascript
for (let i = 0; i < array.length; i++) {
    // Code block to be executed
}
```
Example:
```javascript
const arr = [1, 2, 3, 4];
for (let i = 0; i < arr.length; i++) {
    console.log(arr[i]);
}
```

## While Loop:
```javascript
let i = 0;
while (i < array.length) {
    // Code block to be executed
    i++;
}
```
Example:
```javascript
const arr = [1, 2, 3, 4];
let i = 0;
while (i < arr.length) {
    console.log(arr[i]);
    i++;
}
```

## Do-While Loop:
```javascript
let i = 0;
do {
    // Code block to be executed
    i++;
} while (i < array.length);
```
Example:
```javascript
const arr = [1, 2, 3, 4];
let i = 0;
do {
    console.log(arr[i]);
    i++;
} while (i < arr.length);
```
# Various Methods for Concatenating Arrays in JavaScript

## 1. Using `concat` method:

```javascript
const array1 = [1, 2, 3];
const array2 = [4, 5, 6];

const concatenatedArray = array1.concat(array2);
console.log(concatenatedArray);
```

## 2. Using the spread (`...`) operator:

```javascript
const array1 = [1, 2, 3];
const array2 = [4, 5, 6];

const concatenatedArray = [...array1, ...array2];
console.log(concatenatedArray);
```

## 3. Using `push` method with a loop:

```javascript
const array1 = [1, 2, 3];
const array2 = [4, 5, 6];

array2.forEach(element => {
  array1.push(element);
});

console.log(array1);
```

## 4. Using `Array.prototype.push` with the spread operator:

```javascript
const array1 = [1, 2, 3];
const array2 = [4, 5, 6];

array1.push(...array2);
console.log(array1);
```

### 5. Using `Array.prototype.unshift` with the spread operator:

```javascript
const array1 = [1, 2, 3];
const array2 = [4, 5, 6];

array2.unshift(...array1);
const concatenatedArray = array2;
console.log(concatenatedArray);
```
### 6. Flatten Nested Arrays in JavaScript using `flat` Method

```javascript
const another_array = [1, 2, 3, [4, 5, 6], 7, [6, 7, [4, 5]]];
const real_another_array = another_array.flat(Infinity);
console.log(real_another_array);
```

**Output:**
```
[1, 2, 3, 4, 5, 6, 7, 6, 7, 4, 5]
```

Choose the method that suits your preferences and coding style. The spread operator is often favored for its conciseness and readability.
# **Exploring Array Operations in JavaScript: Array Type Check, Array Conversion, and Array Creation**

1. `console.log(Array.isArray("Hitesh"))` - This checks whether the value `"Hitesh"` is an array. The output will be `false` because `"Hitesh"` is a string, not an array.

2. `console.log(Array.from("Hitesh"))` - This converts the string `"Hitesh"` into an array by creating an array with each character of the string as an element. The output will be `["H", "i", "t", "e", "s", "h"]`.

3. `console.log(Array.from({name: "hitesh"}))` - This attempts to convert the object `{name: "hitesh"}` into an array using `Array.from()`. However, since the argument passed isn't an iterable, the output will be an empty array: `[]`.

4. `let score1 = 100 let score2 = 200 let score3 = 300 console.log(Array.of(score1, score2, score3));` - This uses `Array.of()` to create a new array with the values `100`, `200`, and `300` as elements. The output will be `[100, 200, 300]`. `Array.of()` creates an array from its arguments, regardless of their types.

#  Destructuring of Array
```javascript
  // Basic array destructuring
  const numbers = [1, 2, 3, 4, 5];
  
  // Without destructuring
  const first = numbers[0];
  const second = numbers[1];
  const rest = numbers.slice(2); // Extracting the rest of the elements
  
  console.log(first); // Output: 1
  console.log(second); // Output: 2
  console.log(rest); // Output: [3, 4, 5]
  
  // With destructuring
  const [a, b, ...others] = numbers;
  
  console.log(a); // Output: 1
  console.log(b); // Output: 2
  console.log(others); // Output: [3, 4, 5]
```


```javascript
const mySym = Symbol("key1");

const JsUser = {
    name: "Hitesh",
    "full name": "Hitesh Choudhary",
    [mySym]: "mykey1",
    age: 18,
    location: "Jaipur",
    email: "hitesh@google.com",
    isLoggedIn: false,
    lastLoginDays: ["Monday", "Saturday"]
};

// Modify the email property
JsUser.email = "hitesh@chatgpt.com";

// Prevent further modifications to the object
Object.freeze(JsUser);

// Attempt to modify the email property (no effect due to Object.freeze)
JsUser.email = "hitesh@microsoft.com";

// Add functions as properties to the JsUser object
JsUser.greeting = function() {
    console.log("Hello JS user");
};

// Corrected syntax for greetingTwo function
JsUser.greetingTwo = function() {
    console.log(`Hello JS user, ${this.name}`);
};

// Display the output of functions
console.log(JsUser.greeting()); // Prints: Hello JS user, undefined
console.log(JsUser.greetingTwo()); // Prints: Hello JS user, Hitesh

// Creating an object using object literal notation
const tinderUser = {
    id: "123abc",
    name: "Sammy",
    isLoggedIn: false
};

// Creating a nested object
const regularUser = {
    email: "some@gmail.com",
    fullname: {
        userfullname: {
            firstname: "hitesh",
            lastname: "choudhary"
        }
    }
};

// Object spreading to combine properties from obj1 and obj2
const obj3 = {...obj1, ...obj2};

// Array of objects with id and email properties
const users = [
    { id: 1, email: "h@gmail.com" },
    { id: 1, email: "h@gmail.com" },
    { id: 1, email: "h@gmail.com" }
];

// Using Object.keys, Object.values, and Object.entries methods
console.log(Object.keys(tinderUser));    // Output: ["id", "name", "isLoggedIn"]
console.log(Object.values(tinderUser));  // Output: ["123abc", "Sammy", false]
console.log(Object.entries(tinderUser)); // Output: [["id", "123abc"], ["name", "Sammy"], ["isLoggedIn", false]]

// Checking if a property exists in tinderUser
console.log(tinderUser.hasOwnProperty('isLoggedIn')); // Output: true

// Object destructuring to extract the courseInstructor property
const {courseInstructor: instructor} = course;

// Logging the value of instructor
console.log(instructor);

// Representation of an array containing three empty objects
[
    {},
    {},
    {}
]

```
# Creating an Object with a Read-Only Property
```javascript
const myObject = {};

Object.defineProperty(myObject, 'readOnlyProperty', {
    value: 'This is a read-only property',
    writable: false,  // Setting writable to false makes the property read-only
    enumerable: true, // You can set enumerable to false if you want to hide the property in for...in loops
    configurable: false // Setting configurable to false prevents further modifications to the property
});

console.log(myObject.readOnlyProperty); // Outputs: "This is a read-only property"

// Attempting to modify the read-only property will throw an error
// myObject.readOnlyProperty = 'New Value';  // This will throw an error

// Attempting to redefine the property will throw an error
// Object.defineProperty(myObject, 'readOnlyProperty', { value: 'New Value' }); // This will throw an 
```
# Object creation using shorthand notation

```javascript
const name = "rohit";
const age = 30;

// Object creation using shorthand notation
const person = { name, age };

console.log(person);  // { name: 'rohit', age: 30 }
```

In this example, the object `person` is created using the shorthand notation, where the property `name` takes its value from the variable `name`. Adjust the code according to your specific use case.

# Exploring Object Destructuring in JavaScript

### Object Destructuring:

```javascript
// Example object
const person = {
    firstName: "John",
    lastName: "Doe",
    age: 30,
    address: {
        city: "New York",
        country: "USA"
    }
};

// Destructuring assignment
const { firstName, lastName, age, address: { city, country } } = person;

// Using the extracted values
console.log(firstName);  // "John"
console.log(lastName);   // "Doe"
console.log(age);        // 30
console.log(city);       // "New York"
console.log(country);    // "USA"
```

In this example, the variables `firstName`, `lastName`, `age`, `city`, and `country` are assigned the corresponding values from the `person` object.

### Default Values:

You can also provide default values in case the property is undefined:

```javascript
const { firstName, lastName, age, gender = "Unknown" } = person;
console.log(gender);  // "Unknown" (if the 'gender' property is not present in 'person')
```

### Renaming Variables:

You can rename the variables during destructuring:

```javascript
const { firstName: fName, lastName: lName } = person;
console.log(fName);  // "John"
console.log(lName);  // "Doe"
```

This syntax is especially useful when dealing with function parameters or extracting values from complex nested objects.

# Understanding the JavaScript `this` Keyword 
In JavaScript, the this keyword is a special keyword that refers to the object on which a method is being invoked or the context in which a function is called. The value of this is determined at runtime, depending on how a function is called.

The behavior of this can be a bit tricky, and it is influenced by the following factors:

1. Global Context:
   When this is used outside of any function or method, it refers to the global object. In a web browser, the global object is typically window.
```javascript
      console.log(this); // Refers to the global object (e.g., window in a browser)
   
```
2. Function Context:
   Inside a function, the value of this depends on how the function is called.

   - Regular Function Call:
     If a function is called as a standalone function (not a method or part of an object), this refers to the global object.
```javascript
          function exampleFunction() {
         console.log(this);
     }

     exampleFunction(); // Refers to the global object (e.g., window in a browser)
     
```
   - Method Call:
     When a function is a method of an object, this refers to the object on which the method is invoked.
     
```javascript
         const obj = {
         method: function() {
             console.log(this);
         }
     };

     obj.method(); // Refers to the object 'obj' 
```

3. Constructor Call:
   When a function is used as a constructor with the new keyword, this refers to the newly created instance.

```javascript
      function ConstructorExample() {
       this.property = "some value";
   }

   const instance = new ConstructorExample();
   console.log(instance.property); // Outputs "some value"

```

4. Event Handlers:
   In event handler functions, this often refers to the element that triggered the event.
   
```javascript
      document.getElementById("myButton").addEventListener("click", function() {
       console.log(this); // Refers to the button element
   });
```

It's important to be aware of the different contexts in which this can be used to understand its value correctly. The arrow function in JavaScript behaves differently regarding this, as it does not have its own this and instead inherits it from the surrounding lexical scope.

## Understanding the JavaScript `new` Keyword

In JavaScript, the new keyword is used to create instances of user-defined objects (instances of constructor functions). It is an operator that initializes a new object based on a constructor function. Here's how it generally works:

1. Constructor Function:
   You define a constructor function that serves as a blueprint for creating objects. This function typically initializes properties or performs setup tasks.
```javascript
      function Person(name, age) {
       this.name = name;
       this.age = age;
   }
   
```
2. Creating an Instance:
   You use the new keyword to create an instance of the object based on the constructor function.
```javascript
      const person1 = new Person("John", 30);
   
```
   The new keyword does the following:
   - Creates a new empty object.
   - Sets the this value of the constructor function to the newly created object.
   - Executes the constructor function, which initializes properties on the object.
   - Returns the created object.

   Now, person1 is an instance of the Person object with the specified properties.

3. Accessing Properties:
   You can access the properties of the created object.
```javascript
      console.log(person1.name); // Outputs: "John"
   console.log(person1.age);  // Outputs: 30
```

Here's a more complete example:
```javascript
  function Person(name, age) {
      this.name = name;
      this.age = age;
      this.sayHello = function() {
          console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
      };
  }
  
  const person1 = new Person("John", 30);
  const person2 = new Person("Jane", 25);
  
  person1.sayHello(); // Outputs: "Hello, my name is John and I am 30 years old."
  person2.sayHello(); // Outputs: "Hello, my name is Jane and I am 25 years old."
```

In this example, Person is a constructor function, and person1 and person2 are instances of the Person object created using the new keyword. Each instance has its own set of properties and methods defined in the constructor function.

# Function in JS
JavaScript functions organize, reuse code, handle events, async tasks, return values, and enable encapsulation, abstraction, and scope management for flexible programming.

1. **Function Declarations:**
   ```javascript
   function myFunction() {
       // code here
   }
   ```

2. **Function Expressions:**
   ```javascript
   var myFunction = function() {
       // code here
   };
   ```

3. **Arrow Functions (ES6 and later):**
   ```javascript
   const myFunction = () => {
       // code here
   };
   ```

4. **Anonymous Functions:**
   Functions without a name. Can be used as function expressions.
   ```javascript
   var result = function() {
       // code here
   };
   ```

5. **IIFE (Immediately Invoked Function Expression):**
   ```javascript
   (function() {
       // code here
   })();
   ```

6. **Generator Functions (ES6 and later):**
   ```javascript
   function* generatorFunction() {
       // code here
   }
   ```

7. **Callback Functions:**
   Functions passed as arguments to other functions, often used in asynchronous operations.
   ```javascript
   function fetchData(callback) {
       // code to fetch data
       callback(data);
   }
   ```

8. **Constructor Functions:**
   Used to create objects and can be invoked with the `new` keyword.
   ```javascript
   function Person(name, age) {
       this.name = name;
       this.age = age;
   }

   var person1 = new Person("John", 25);
   ```

9. **Recursive Functions:**
   Functions that call themselves.
   ```javascript
   function factorial(n) {
       if (n === 0 || n === 1) {
           return 1;
       } else {
           return n * factorial(n - 1);
       }
   }
   ```

10. **Higher-Order Functions:**
    Functions that take other functions as arguments or return functions.
    ```javascript
    function higherOrderFunction(callback) {
        // code here
        callback();
    }
    ```
# Shorthand Syntax for Arrow Functions in JavaScript
Arrow functions in JavaScript offer shorthand syntax for concise code. Here are some examples of shorthand usage:

1. **Implicit Return:**
   If the function body has a single expression, it's implicitly returned without using the `return` keyword.
   ```javascript
   const double = (x) => x * 2;
   ```

2. **Single Parameter:**
   When a function has only one parameter, you can omit the parentheses.
   ```javascript
   const square = x => x * x;
   ```

3. **Returning Object Literal:**
   To return an object literal directly, enclose it in parentheses to distinguish from a block.
   ```javascript
   const createPerson = (name, age) => ({ name, age });
   ```

4. **No Parameters:**
   For functions with no parameters, use empty parentheses.
   ```javascript
   const sayHello = () => console.log("Hello!");
   ```

5. **Implicit Binding of `this`:**
   Arrow functions don't have their own `this` context, so they inherit `this` from the surrounding code.
   ```javascript
   function Counter() {
       this.count = 0;
       setInterval(() => {
           this.count++;
           console.log(this.count);
       }, 1000);
   }
   ```
# Memory Allocation in JavaScript

1. **Primitive Data Types:**
    - **Stored in Stack:** `string`, `number`, `boolean`, `null`, `undefined`, `BigInt`, `symbol`.
    - **Pass by Value:** When assigning or passing these, a copy of the actual value is made. Modifying one variable doesn’t affect another holding the same value.

2. **Reference/Non-primitive Data Types:**
    - **Stored in Heap:** `object`, `array`, `function`.
    - **Pass by Reference (Reference):** Variables hold references to memory locations where the actual data resides. Assigning or passing these doesn't create a copy of the entire data but a reference to the original.

3. **Dynamic Typing in JavaScript:**
    - Data types are determined implicitly based on the assigned value.
    - Variables can hold different types of values during the program's execution.

### Example:
```javascript
// Primitive types (stored in stack, pass by value)
let num1 = 10; // 'num1' holds the value 10
let num2 = num1; // 'num2' gets a copy of the value from 'num1'

num1 = 20; // Changing 'num1' doesn't affect 'num2'

// Reference types (stored in heap, pass by reference)
let arr1 = [1, 2, 3]; // 'arr1' holds a reference to an array in the heap
let arr2 = arr1; // 'arr2' now references the same array as 'arr1'

arr1.push(4); // Changes made via 'arr1' are reflected in 'arr2' too

// Dynamic Typing
let dynamicVar = 42; // Initially, 'dynamicVar' holds a number
dynamicVar = "Hello"; // Later, 'dynamicVar' holds a string
```

Understanding these principles is fundamental for effectively working with JavaScript's dynamic typing and memory allocation strategies.


