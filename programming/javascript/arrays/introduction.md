---
title: Introduction to Arrays
description: Create and access values in JavaScript arrays.
order: 1
---

# Introduction to Arrays

An **array** is a collection that allows you to store multiple values in a single variable.

For example, instead of creating separate variables for each fruit:

```javascript
const fruit1 = "apple";
const fruit2 = "banana";
const fruit3 = "cherry";
```

you can store them together in an array:

```javascript
const fruits = ["apple", "banana", "cherry"];
```

Here, `fruits` contains three values:

```text
apple
banana
cherry
```

## Creating an Array

You can create an array using square brackets `[]`:

```javascript
const fruits = ["apple", "banana", "cherry"];
```

An array can contain different types of values:

```javascript
const values = ["hello", 42, true];
```

However, it is usually better to keep related values together.

For example:

```javascript
const ages = [18, 21, 25, 30];
```

## Accessing Array Items

Each item in an array has an **index**.

JavaScript arrays use **zero-based indexing**, which means the first item has an index of `0`.

```text
Index:    0         1          2
          ↓         ↓          ↓
Value:  apple    banana     cherry
```

You can access an item using its index:

```javascript
const fruits = ["apple", "banana", "cherry"];

console.log(fruits[0]); // "apple"
console.log(fruits[1]); // "banana"
console.log(fruits[2]); // "cherry"
```

Trying to access an index that doesn't exist returns `undefined`:

```javascript
console.log(fruits[5]); // undefined
```

## Array Length

The `length` property tells you how many items are currently in an array.

```javascript
const fruits = ["apple", "banana", "cherry"];

console.log(fruits.length); // 3
```

The index of the last item is always one less than the array's length:

```javascript
console.log(fruits[fruits.length - 1]); // "cherry"
```

This is useful when you don't know how many items an array contains.

## Adding Items

You can use the `push()` method to add an item to the **end** of an array.

```javascript
const fruits = ["apple", "banana", "cherry"];

fruits.push("mango");

console.log(fruits);
```

Output:

```text
["apple", "banana", "cherry", "mango"]
```

The array now contains four items:

```javascript
console.log(fruits.length); // 4
```

You can also add multiple items at once:

```javascript
fruits.push("orange", "grape");

console.log(fruits);
```

Output:

```text
["apple", "banana", "cherry", "mango", "orange", "grape"]
```

## Quick Example

Here is a small example combining what we have learned:

```javascript
const fruits = ["apple", "banana", "cherry"];

console.log(fruits[0]);       // "apple"
console.log(fruits.length);   // 3

fruits.push("mango");

console.log(fruits);
console.log(fruits.length);   // 4
```

## Key Points

> **Remember:**
>
> * Arrays store multiple values in a single variable.
> * Arrays use square brackets `[]`.
> * Array indexes start at `0`.
> * Use `array[index]` to access an item.
> * Use `array.length` to get the number of items.
> * Use `array.push()` to add items to the end.

## What's Next?

Now that you know how to create and access arrays, you can learn about other useful array methods such as `pop()`, `shift()`, `unshift()`, and `splice()`.
