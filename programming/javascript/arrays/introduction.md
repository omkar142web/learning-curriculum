---
title: Introduction to Arrays
description: Create and access values in JavaScript arrays.
order: 1
---

# Introduction to Arrays

An array is an ordered list of values.

```javascript
const fruits = ["apple", "banana", "cherry"];
```

Access items by index:

```javascript
console.log(fruits[0]); // "apple"
console.log(fruits[2]); // "cherry"
```

## Array length

The `length` property tells you how many items are in an array:

```javascript
console.log(fruits.length); // 3
```

## Adding items

Use `push` to add an item to the end of an array:

```javascript
fruits.push("mango");

console.log(fruits); // ["apple", "banana", "cherry", "mango"]
```
