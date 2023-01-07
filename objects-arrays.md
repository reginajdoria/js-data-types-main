[![General Assembly Logo](https://camo.githubusercontent.com/1a91b05b8f4d44b5bbfb83abac2b0996d8e26c92/687474703a2f2f692e696d6775722e636f6d2f6b6538555354712e706e67)](https://generalassemb.ly/education/web-development-immersive)


# Introduction to JavaScript: Reference Data Types 

## Learning Objectives

- Start working with Arrays in JavaScript.
- Get familiar with and work with Array methods.
- Start working with Objects in JavaScript.
- Work with Object methods.

# Reference Data Types in JavaScript

Reference data types are those which can store multiple values. In JavaScript they are called `arrays` and `objects`.

## Arrays

Arrays are an ordered collection of related data and are organized by index.

- Indexing begins at 0 (e.g., first element in an array has an index of 0, the
  second has an index of 1, and so on).

We instantiate an array like this...

```js
const mountRushmore = ["Washington", "Jefferson", "Roosevelt"];
```

And access its values like so...

```js
mountRushmore[0];
// => "Washington"

mountRushmore[1];
// => "Jefferson"

mountRushmore[2];
// => "Roosevelt"

mountRushmore.push("Lincoln");
// mountRushmore = [ "Washington", "Jefferson", "Roosevelt", "Lincoln" ]

mountRushmore[3];
// => "Lincoln"
```

You can also place arrays within arrays.

```js
const letters = [["a", "b", "c"], ["d", "e", "f"], ["g", "h", "i"]];
```

<details>
<summary>How would we go about accessing the letter "f" in the above array?</summary>

```js
letters[1][2];
// => "f"
```

</details>

Arrays can also contain any type of data, not just primitives. Arrays can
contain functions and objects!

```js
let mixed = [
  { object: "value" },
  "one string",
  function() {
    console.log("I'm fun")
  },
  0,
  "a second string"
];
```

> The syntax can be hard to read, but how many items are in this array?


## Data Type Methods

Each of the data types we've covered so far has their own "methods". These are
functions that you can run to perform certain operations.

Pay attention to what type you're trying to use a method on. For example, you
can't use string methods on numbers, and vice versa. Each type has its own
methods.


### Array Methods

There are a lot of useful methods that come with JavaScript we can use to
inspect and modify arrays. To learn what some of them are...

- `.length`
- `.push()` / `.pop()`
- `.shift()` / `.unshift()`
- `.indexOf()`
- `.reverse()`
- `.concat()`
- `.join()`
- `.sort()`

> There are many more, but these are the most widely-used.

#### Length method

The `length` method works in an interesting way in Javascript. It is always one more than the highest index in the array.

So `array.length` isn't necessarily the number of items in the array. Consider the following:

```javascript
let a = ['dog', 'cat', 'hen'];
a[100] = 'fox';
a.length; // 101
```

**Remember**: the length of the array is one more than the highest index.

#### Getting data from an array

If you query a non-existent array index, you get `undefined`:

```javascript
let a = ['dog', 'cat', 'hen'];

a[90];
=> undefined
```

#### You Do: Array Practice

1. Write an array that contains the names of the people in breakout room.
2. Get the index of your name in that array (using an array method).
3. Add the IA on duty to the array (using an array method).
4. Combine two arrays

[Here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
is more documentation on arrays.


## Bonus: The Spread Operator

The spread operator `...` allows an expression to be expanded into multiple
elements.

This is useful for separating an array into individual elements...

```js
let dimensions = [10, 5, 2];

// ES5
console.log(dimensions[0], dimensions[1], dimensions[2]);

// ES6
console.log(...dimensions);
```

#### Bonus: Copying Arrays

Variables in JavaScript only store references to arrays rather than the array
itself. Therefore, if we do something like the following, both arrays will be
impacted.

```js
let arr = [1, 2, 3];
let arr2 = arr;

arr2.pop();
arr
// => [1, 2]

arr2
// => [1, 2]
```

The ES6 spread operator makes it really easy to shallow copy arrays in JavaScript,
or create a new array with the same values as the old one.

```js
let arr = [1, 2, 3];
let arr2 = [...arr];

arr2.pop();
arr
// => [1, 2, 3]

arr2
// => [1, 2]
```

We can also copy arrays using the `.slice()` array method.

```js
//ES5 Style
var arr = [1, 2, 3];
var arr2 = arr.slice();
```

## Objects

Objects in javascript are fundamental to the language. Everything is an object.
Aside from the values `null` and `undefined`, **literally in JavaScript is an object**. This will make more sense later.

Like arrays, objects can hold multiple pieces of data of varying types; but unlike arrays, objects use named keys rather than indices to order and access those pieces of data

Example: A car has properties, a type of engine, a color, a certain number of seats etc. Following the same logic, a JavaScript object may have **properties** and **values** for these properties.
### Collection of key-value pairs

The following is an example of an object's key-value pair syntax:

```javascript
const car = {
  make: 'Honda',
  model: 'Civic',
  year: 1989,
  engine: '1.5 liter',
  seats: 5,
  color: 'grey'
}
```
> "make" is the key, while "Honda" is the value

> Objects must have both a key and a value - neither can be empty.

Unlike arrays, objects use *named keys* rather than ordered indexes. Each piece of data is bound to its key, rather than assigned an index. The data is not sequential.

We could store this same information in an array like this:

```
const car = ['Honda', 'Civic', 1989]
```

But with the array above, we don't know what the values mean. Does 'Civic' refer to the name of the owner, or the model of the vehicle?


To declare an object, just write `{}`

```js
let students = {};
```

Objects **MUST** contain key/value pairs to be valid syntax. The key and value
are separated by a `:`

```js
let students = {
  name: "Jimmy"
};
```

The value can be any type, including arrays, strings, numbers, even other
objects!

```js
let sei = {
  students: ["Jimmy", "Frank"],
  curriculum: {
    hard: true,
    valuable: "Absolutely"
  }
};
```

You can access properties of objects by their names.

```js
console.log(sei.students);
// ["Jimmy", "Frank"]
console.log(sei.curriculum.hard);
// true
console.log(sei.curriculum.valuable);
// "Absolutely"
```

We'll cover more about objects in a later lesson, but these are the basics.

### You do: Objects exercise

Build the biggest, baddest SEI student object that you can and console.log each of the
properties in it.

- **Bonus** - One key value pair contains an array
- **Double Bonus** - one key value pair contains another object

## Closing

## Additional Practice + Resources

- [Khan Academy Intro to Programming JS](https://www.khanacademy.org/computing/computer-programming/programming#intro-to-programming)
- [You Don't Know JS: Up & Going](https://github.com/getify/You-Dont-Know-JS/blob/master/up%20&%20going/README.md#you-dont-know-js-up--going)
- [Eloquent JavaScript](http://eloquentjavascript.net/)
- [How to Deep Copy Arrays & Objects in JavaScript](https://medium.com/javascript-in-plain-english/how-to-deep-copy-objects-and-arrays-in-javascript-7c911359b089)
-----
### Previous: [Primitive Data Types](primitive-data-types.md)
