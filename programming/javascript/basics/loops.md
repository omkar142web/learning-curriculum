---

title: Loops
description: Repeat a block of code multiple times without writing the same code over and over.
order: 4
---

# Loops

Loops let you **repeat a block of code** multiple times without having to write the same code again and again.

## `for` Loop

A `for` loop is useful when you know **how many times** you want to repeat something.

```javascript
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

This loop runs **5 times** and prints:

```text
0
1
2
3
4
```

### How It Works

A `for` loop has three main parts:

```javascript
for (initialization; condition; update) {
  // code to repeat
}
```

* **Initialization** — runs once before the loop starts.
* **Condition** — checked before each iteration. The loop continues while it is `true`.
* **Update** — runs after each iteration.

In the example:

```javascript
let i = 0; // initialization
i < 5;     // condition
i++;       // update
```

The value of `i` starts at `0` and increases by `1` after each iteration. The loop stops when the condition `i < 5` becomes `false`.
:::
