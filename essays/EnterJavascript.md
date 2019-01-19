---
layout: essay
type: essay
title: "Enter Javascript"
date: 2019-01-18
labels:
  - Javascript
  - Weak vs Strongly typed
  - Variable Assignment
  
---

My first programming language that I could call myself proficient with was Java. I fell in love with the structure, the verbosity, and the overall standard java library. Everything seems well thought out and put together in that language. Now, enter Javascript. At first it seems like the wild west of programming languages. One example is instead of implicitly declaring a variable and declaring its type like in java, it's inferred. This is called being a weakly typed language and is a bit worrisom at first. I'm going to go over a few of the differences someone coming from java might have issue with migrating to javascript, mainly var, let, const, and truthiness.

In Java we would do this if we wanted to declare and assign an integer value of 0 to a variable
```java
int value = 0; // example of being strongly typed, we declare the data type int
```

in Javascript you can do it in a multitude of ways.

```js
value = 0; //global
let value = 0; //block scoped
const value = 0; //block scoped and can't be reassigned
var value = 0; //scoped to function or global, and hoisted
```

<h2>Var</h2>
All of the different "types" you can use in Javascript are not referring to their data type, but instead their behavior. The data type of the variable is inferred by what is assigned to it, it can be anything from a primitive int to a Object. In regards to it's scope, if you use var the variable will either be scoped to the function it's inside of or global.

```js
console.log(i); //ME: there's no way this can work! JS: "Hold my beer!"
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
console.log(i); //error
```

In the above code snippit it seems were back to sanity! console.log(i) will cause javascript to throw an error. Why? because let is block scoped, meaning it lives only within its scope.

```js
const i = 0;
i = 3; //error 

for(const j = 0; j < 10; j++) { //error
  
}

{
  const k = 0; // is defined in it's own scope
}

console.log(k); //error
```

In the example above we will get a multitude of errors. First being with `i = 3;`. Const acts like a constant does in most programming languages as it can't be reassigned. Another error will be in the for loop. Since the reference cannot be changed, the value of j in this example cannot be changed, which is not good in the case of for loops. const is also block scoped. One thing not to get confused about is that const does not mean immutable. If you declare an object to be const, you can still change the values within that object, you just cannot point it to a different instance.

<h2>Truthiness</h2>
  
One thing that javascript has that kind of mind boggles me is the results of == vs === and truthy vs falsy values. So to start off what exactly is a truthy or falsy value? Well a falsy value is anything that has the values of
```
false
0
'' or "" //an empty string)
null
undefined
NaN
```
  
So what is a truthy value might you ask? Literally everything else. Take the example below

```js
if("Do aliens exist?"){
  console.log("THEY DO!") //will print
}
```
  
Now with regards to == and === the former is a loose equality testing. Basically meaning if it can be converted to the same "type" and compared it will return true. === is strict equality testing. Meaning if they are not the same type it will return false.
  
```js
  
let x = 1;
let y = "1";
  
if(x == y){
  console.log("x == y is true"); // will print
}
  
if(x === y) {
  console.log("x === y is true"); // will not print
}
```
  
In the above example you can see that 'x == y' will loosely evaulate if they are equal, and then return true.
 
  

<h2>Opinion</h2>

Now, what is my opinion on Javascript might you ask? Well if it was before ES6 and I only had var to work with I might have screamed. But it seems that with the newer standards javascript is bringing a little bit more structure to the style in which people use it. As of right now, I think I like it, but as I delve furthur into its depths, I'm sure there will be oddities that rub me the wrong way, but that's true of any language. As long as you keep in mind a few of the oddities and stick to the newer ES6 standard I don't see any issues with javascript that would make me absolutely hate it. I do however prefer a more structured language like Java, but I can definitely see the need and the usefulness of javascript.
  



