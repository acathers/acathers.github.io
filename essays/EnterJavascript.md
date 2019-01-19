---
layout: essay
type: essay
title: "Enter Javascript"
date: 2019-01-18
labels:
  - Javascript
  - Weak vs Strongly typed
  
---

My first programming language that I could call myself proficient with was Java. I fell in love with the structure, the verbosity, and the overall standard java library. Everything seems well thought out and put together in that language. Now, enter Javascript. At first it seems like the wild west of programming languages. One example is instead of implicitly declaring a variable and declaring its type, it's inferred. This is called being a weakly typed language 

In Java we would do this
```java
int value = 0;
```

in Javascript you can do it in a multitude of ways.

```js
value = 0;
let value = 0;
const value = 0;
var value = 0;
```

<h2>Var</h2>
All of the different "types" you can use in Javascript are not referring to their data type, but instead their behavior. The data type of the variable is inferred by what is assigned to it, it can be anything from a primitive int to a Object. In regards to it's scope, if you use var the variable will either be scoped to the function it's inside of or global.

```js
console.log(i);
for(var i = 0; i < 10; i++){
}

console.log(i);
```

The above snippet shows a bit of oddities with using var. First, how on earth am I able to use the variable i before it was declared? That is due to something called hoisting. With javascript if you use var, the declaration, not the assignment, is hoisted to the top. So it won't error but it will print undefined since only the declaration was hoisted.

Now how did I use the variable outside of the for loop? Thats explained by vars scoping rules. It is either local to the function or global. Since it was no declared within a function it is a global variable and thus is visible to all.

<h2>Let and Const</h2>

With the introduction of the ES6 standard let and const were introduced. Why might you ask? I can only assume it was to reign in vars unpredicable nature as it seems extremely easy to abuse. Both let and const brought back block scoping that we all know and love.

```js
for(let i = 0; i < 10; i++ {
    
    }
console.log(i);
```

In the above code snippit it seems were back to sanity! console.log(i) will cause javascript to throw an error. Why? because let is block scoped, meaning it lives only within its scope.

```js
const i = 0;
i = 3;

for(const j = 0; j < 10; j++) {
  
}

{
  const k = 0;
}

console.log(k);


```

In the example above we will get a multitude of errors. First being with `i = 3;`. Const acts like a constant does in most programming languages as it can't be reassigned. Another error will be in the for loop. Since the reference cannot be changed, the value of j in this example cannot be changed, which is not good in the case of for loops. const is also block scoped. One thing not to get confused about is that const does not mean immutable. If you decalre a object to be const, you can still change the values within that object, you just cannot point it to a different instance.
  



