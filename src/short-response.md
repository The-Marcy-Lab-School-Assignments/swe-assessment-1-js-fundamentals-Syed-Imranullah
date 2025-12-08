# Mod 1 Assessment - Short Response Section

Write your responses directly in this file. Follow markdown formatting guidelines.

---

## Section 1: Short Response

### Question 1

The code throws a ReferenceError.
This happens because ``currentStatus`` is declared with `let` inside the `if` and `else` blocks. Variables declared with `let` are block-scoped, meaning they only exist inside the `{ }` where they’re defined.

So when the code reaches `console.log(currentStatus)`, that variable doesn’t exist in that outer scope, which triggers the error.

**fixed version is down below**

```javascript
const react = (isReuben) => {
  let currentStatus;

  if (isReuben) {
    currentStatus = 'Everything is just fine';
  } else {
    currentStatus = 'Time to panic.';
  }

  console.log(currentStatus);
}

react(true);
```

### Question 2
The code logs "Michael Jordan". This happens because `bestPlayer` is an object, and when we assign `theGOAT = bestPlayer`, both variables point to the same object in memory.

So when we update `BestPlayer.name` to "Michael Jordan", we’re actually changing the one shared object. Since theGOAT references that same object, theGOAT.name will also reflect the updated value. That’s why the output is "Michael Jordan".

### Question 3
The code prints: 
Paul is the hardest working person in the room.
Laisha is also the hardest working person in the room.

This happens because the function creates its own version of the variable. We first have a global variable called `theHustler` with the value 'Laisha'. Then inside the `shoutOut` function, we declare another `theHustler` with the value 'Paul'.

JavaScript always uses the variable in the closest scope.
So when the function runs, `${theHustler}` refers to 'Paul', because that’s the variable inside the function. After the function finishes, the second `console.log` uses the outer `theHustler`, which is 'Laisha'.

That’s why the output shows Paul first, then Laisha.

### Question 4
Rest parameters let a function accept any number of arguments and put them into a single array. This is useful when you don’t know how many values will be passed in.

To make a parameter a rest parameter, use three dots `(...) ` before it's name, like `(...numbers)`. All extra arguments passed to the function are collected into the array numbers. You can then loop through it or use array methods.

Example shown below: 

```javaScript

const sum = (...numbers) => {
  let total = 0;
  for (const num of numbers) {
    total += num;
  }
  return total;
};

sum(1, 2, 10); // 13
sum(5); // 5
sum(100, 200, 800, 1, 1, 1); // 1103
```


### Question 5
Scope is the area in your code where a variable can be accessed. Some variables are global (usable anywhere), and some are local (usable only inside a function or block).

You can think of scope like a backpack. If you put something in your backpack (local scope), only you can use it. If it’s on the table in the room (global scope), everyone in the room can use it.

```javaScript
const calculateDiscount = (price) => {
  let discountRate;
  if (price > 100) {
    discountRate = 0.1; // discountRate is accessible inside the function
  } else {
    discountRate = 0.05;
  }

  const discount = price * discountRate; // discount is also local to the function
  return price - discount;
};

console.log(calculateDiscount(150)); // 135
```

### Question 6
Modules are separate files that hold specific pieces of code, like functions or data, which you can export and import into other files.
Modules make code organized, reusable, and easier to maintain. They also help prevent variable and function conflicts by keeping related code in one place.

Example shown below: 
```javaScript 

//math.js
const add = (a, b) => a + b;
module.exports = add;

const add = require('./mathUtils');
console.log(add(2, 3)); // 5
```
The function add is defined and exported in math.js using module.exports.

In another file, we import it with require('./math') and use it.

### Question 7
After the code runs:
`fruits` will be:
`['apple', 'banana', 'cherry', 'date']`
`fruitsMinusOne` will be:
`['apple', 'banana', 'cherry']`
The original array fruits does not change, and fruitsMinusOne holds a new array with the last element removed.

We make a copy of the array to avoid changing the original input. A pure function should not have side effects, so copying ensures the function only works with its own data.

We want functions to be pure so they don’t change other things in the program. This makes them easier to understand, predictable, and safer to use.

### Question 8

I would use an object to represent a single item in the cart. Each item has multiple pieces of information, like `name`, `price`, and `quantity`, so an object makes it easy to group all these properties together.

I would use an array to hold all the items. Each element in the array is an item object. Arrays make it easy to add, remove, or loop through items in the cart.

```javaScript 
const shoppingCart = [
  { name: 'Apple', price: 1, quantity: 3 },
  { name: 'Banana', price: 0.5, quantity: 5 },
  { name: 'Orange', price: 0.75, quantity: 2 }
];
```