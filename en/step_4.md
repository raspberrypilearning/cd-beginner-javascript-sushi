## Random colours

Now you can select a button and change its colour, which is cool, but you need to be able to choose colours _at random_ to make the game work. Luckily, JavaScript can pick random numbers for you and, with a little work, you can make sure they're between `0` and `255`. The best way to handle this is to make a function to get you a random colour value (a number between `0` and `255`).

--- collapse ---
---
title: JavaScript and random numbers
---
JavaScript has a built-in function called `Math.random` that you can use to produce a random decimal number between `0` and `1`. By using a little multiplication you can get a random number between `0` and any other number.

For example, to get a number between `0` and `100` you would multiply the result of `Math.random` by `100`, like this:

```JavaScript
myRandomNumber = Math.random()*100;
```
This works because the smallest random number will be `0` and `0*100=0`. The largest will be `1` and `1*100=100`. Anything in-between will give you a number in-between `0` and `100`. For example `0.25*100=25`.

Of course, there is a problem if you only want whole numbers (integers). If the random number produced by `Math.random()` is something like `0.245834` then multiplying it by `100` won't get you a nice neat answer! You'll get `24.5834`, which will not make sense as a colour. Luckily, JavaScript has another built-in function that can help out here! `Math.round` will round up or down depending on the decimal values of the number and give you a whole number as a result! So, to get a whole number between `0` and `100`, for example, you would write:

```JavaScript
myRandomNumber = Math.round(Math.random()*100);
```
--- /collapse ---

--- task ---
Create a function called `makeColourValue` that uses JavaScript's built-in `Math.random` and `Math.round` functions to get a random number between `0` and `255` and **return** it. When a function returns a value it can be stored or used by the code that called the function.

```JavaScript
function makeColourValue(){
    return Math.round(Math.random()*255);
}
```
--- /task ---

Now it's time to use the function you just created.

--- task ---
Update the code you used to set the button colour so you use three variables, named `red`, `green` and `blue`, with random colours picked by your `makeColourValue` function to set the button's colour.

```JavaScript
var red = makeColourValue();
var green = makeColourValue();
var blue = makeColourValue();

setButtonColour(buttons[0], red, green, blue);
```
--- /task ---
Now reload the page a few times and watch the button change colour!