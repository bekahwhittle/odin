### Javascript Learnings

#### Variables

`const` are immutable and always constant. 

`let` or `var` are mutable variables.

Example: 

``` js
const COLOR_PINK = #F1F1F1;

let pink = COLOR_PINK;
console.log(pink);
```

`COLOR_PINK` won't change - it'll always remain that hex value. 
`pink` might change - maybe we use a different constant or we switch 'pink' as we write. 

#### Functions

A function is a reusable block of code. Without functions we'd have a very long file ahead of us and the code would be very wet, not DRY.

To use your function you 'invoke' it. This means you call it, like a a dog's name. The dog doesn't know their name until you call it.

```js
function myFunction() {
    alert("Howdy Texas");
}

myFunction();
```

At the bottom of the above snippet is where we're actually running our function, now that we've invoked the function we'll get the return of its contents.

To use parameters inside a function you must invoke those into the functions parantheses. 

```js
function greetUser(greeting, fullName) {
    alert(greeting + fullName);
}

greetUser("Howdy", "Rebekah");
```

Access to your variables within your function will vary, as its dependent on placement. 
If you're attempting to call a variable outside of its scope you won't have access to it. That's like trying to call your dog when their outside your yard, they won't hear you. 

```js
function greetUser() {
    let greeting = "Howdy "
    let fullName = "Bekah!"

    alert(greeting + fullName);
}

greetUser();

alert(greeting + fullName); // <-- that won't work due to being outside of the function. your dog can't hear you - its chasing squirrels!
```

Returning a value within a function can be tricky at first especially as we move to more complex functions. 
Returning a value is as simple as using the keyword: `return`.

#### Problem Solving

Let's start by trying to solve FizzBuzz. 

##### FizzBuzz

> In numerical order, print the numbers a user enters from 1 to their number. If the number is a multiple of 3 print Fizz. If the number is a multiple of 5 print Buzz. And if the number is a multiple of both 3 & 5 print FizzBuzz. 

```js
let answer = parseInt(prompt("Please enter your number"));

for (let i = 1; i <= answer; i++) {
  console.log(i);
}
```

This simple `for loop` allows us to take i, which is starting at 1 and loop through it. We are saying, let i start at 1 and then increment up until it's lesser or equal to our answer. 

```js
let answer = parseInt(prompt("Please enter your number"));

for (let i = 1; i <= answer; i++) {
  if (i % 3 === 0) {
    console.log("Fizz")
  } else if (i % 5 === 0) {
    console.log("Buzz")
  } else if (i % 3 === 0 && i % 5 === 0) {
    console.log("FizzBuzz")
  } else {
    console.log(i);
  }
}
```

Currently with the way the conditionals are set we won't see `FizzBuzz`. Why? Because our program will first check if a number is divisble by 3, then 5, before checking if it's divisible by both. By the time we get to the end of our for loop we already have `Fizz` and `Buzz` printed. 
So, let's go ahead and re-arrange this properly so our program will check if the integer is divisible by both 3 && 5 before moving on to 3, then 5. 

```js
let answer = parseInt(prompt("Please enter your number"));

for (let i = 1; i <= answer; i++) {
  if (i % 3 === 0 && i % 5 === 0) {
    console.log("FizzBuzz")
  } else if (i % 5 === 0) {
    console.log("Buzz")
  } else if (i % 3 === 0) {
    console.log("Fizz")
  } else {
    console.log(i);
  }
}
```

















































