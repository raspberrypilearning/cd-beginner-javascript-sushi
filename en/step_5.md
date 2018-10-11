## Changing all the buttons

Now one button is changing at random, but you want to have all six of them change. Luckily, you don't have to write your code out six times! You can use a **loop** — in this case a `for` loop, which does something a particular number of times — to have JavaScript repeat it, but change one small thing: the number in the square brackets on the `buttons` array. This means that each button in turn will be assigned a totally random colour without you having to worry about how many there are. If you added another three buttons, or another thousand, it would take the same amount of code!

--- task ---
Take your existing code for choosing and setting the colour of a button and wrap a `for` loop around it, using the **loop variable** — normally named `i` (because it's an **i**ntiger) — to pick which of the elements of the `buttons` array you're changing.

```JavaScript
for (var i = 0; i < buttons.length; i++) {

  var red = makeColourValue();
  var green = makeColourValue();
  var blue = makeColourValue();
  
  setButtonColour(buttons[i], red, green, blue);

}
```
--- /task ---
Reload the page a few times and watch those buttons change. Notice that, while you know (because you wrote it that way) that the change is happening one button after the other, it's happening so fast you can't actually see that!

--- collapse ---
---
title: How the for loop works
---
A `for` loop has four parts:

 - The loop variable, which is usually created at the start of the loop and used to count the number of times the loop code has run. This is usually called `i` and is created with the `var i = 0;` piece of the loop code.
 - The test, which is checked to decide whether to run the loop code or not. It's usually something like 'Is the loop variable five or bigger?' or 'Is the loop counter smaller than the number of items in a particular array?'. If the test is true then the loop runs and comes back to the test again. If the test is false then all of the remaining loop code is skipped over and the program continues. In the case of this `for` loop it's the second question —  `i < buttons.length;` —'Is the loop counter smaller than the number of items in a particular array?', in this case the `buttons` array. Notice the `buttons.length` property that tells us how many items are in `buttons`.
 - The actual code that the loop runs, contained inside the braces `{}`. This can be anything you want, and it has access to the current value of the loop variable, which is how you can use it to 'loop over' an array.
 - Back up at the top of the loop is the final piece, a little bit of code that runs once the loop has successfully completed. Usually, this is just adding one to the loop variable you're using to count your progress and that's exactly what this is here too: `i++` is just a shortcut for `i = i + 1`.
--- /collapse ---
