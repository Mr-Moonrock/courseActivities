Ryan Stiverson

# Rest / Spread Operator Exercises
#### In this exercise, you’ll refactor some ES5 code into ES2015.

#### Given this function:

1. Refactor it to use the rest operator & an arrow function:

function filterOutOdds() {
  var nums = Array.prototype.slice.call(arguments);
  return nums.filter(function(num) {
    return num % 2 === 0
  });
}

My answer=
Const filterOutOdds = (…nums) => nums.filter => (nums % 2 === 0)

Correct Answer =
Const filterOutOdds = (…args) => args.filter => (v => v % 2 === 0)

2. findMin: Write a function called findMin that accepts a variable number of arguments and returns the smallest argument.

Make sure to do this using the rest and spread operator.

findMin(1,4,12,-3) // -3
findMin(1,-1) // -1
findMin(3,1) // 1

const findMin = (...nums) => {
return nums.reduce((min, num) => {
return num < min ? num : min;
});
};

Answer= const findMin = (...args) => Math.min(...args)

3. mergeObjects: Write a function called mergeObjects that accepts two objects and returns a new object which contains all the keys and values of the first object and second object.

mergeObjects({a:1, b:2}, {c:3, d:4}) // {a:1, b:2, c:3, d:4}

const mergeObjects = (...objs) => {
return objs.reduce((acc, obj) => {
Object.keys(obj).forEach((key) => {
acc[key] = obj[key];
});
return acc;
}, {});
};

4. doubleAndReturnArgs: Write a function called doubleAndReturnArgs which accepts an array and a variable number of arguments. The function should return a new array with the original array values and all of additional arguments doubled.

doubleAndReturnArgs([1,2,3],4,4) // [1,2,3,8,8]
doubleAndReturnArgs([2],10,4) // [2, 20, 8]

const doubleAndReturnArgs = (arr, ...args) => [
...arr,
...args.map((x) => x * 2),
];

## Slice and Dice!

#### For this section, write the following functions using rest, spread and refactor these functions to be arrow functions! Make sure that you are always returning a new array or object and not modifying the existing inputs.

1. /\*_ remove a random element in the items array
and return a new array without that item. _/

const removeRandom = items => {
let index = Math.floor(Math.random() \* items.length);
return [...items.slice(0, index), ...items.slice(index + 1];
}
}

2. /\*_ Return a new array with every item in array1 and array2. _/

function extend(array1, array2) {
return [...array1,...array2]
}

3. /\*_ Return a new object with all the keys and values
from obj and a new key/value pair _/

const addKeyVal = (obj, key, val) => {
let newObj = {... obj}
newObj[key] =val;
return newObj;
}

4. /\*_ Return a new object with a key removed. _/

const removeKey = (obj,key) => {
let newObj = {...obj}
delete newObj[key]
return newObj;
}
}

5. /\*_ Combine two objects and return a new object. _/

const combine = (obj1, obj2) => {
return {...obj1, ...obj2}
}

6. /\*_ Return a new object with a modified key and value. _/

const update = (obj, key, val) => {
let newObj = {... obj}
newObj[key] = val;
return newObj;
}
