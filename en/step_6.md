## Picking & checking the answer

Now your game is randomising the colours every time it reloads, you need to pick one colour to be the winning answer and make sure that when the player clicks on the right button, they know they've won.

To do this you need to:

 - Pick a colour to be the right answer
 - Display the rgb values for that colour to the user
 - Make sure that when the winning button is clicked, the user gets some sort of message about it

The easiest way to pick a colour to be the right answer is to pick a _button_ to be the right answer and just use its colour.

--- task ---
You already know how to pick a number at random, so pick a number that could be the position of a button in `buttons`.

Add this code in just before your `for` loop.

```JavaScript
var answerButton = Math.round(Math.random() * buttons.length);
```
--- /task ---

Next, you need to display the rgb values for that button. You'll have those three values during the `for` loop, as you're setting the colour of the button, so that's the right time to set the message too. Of course, you'll need to make sure that the message setting code only runs when the button is the `answerButton` your code has picked. This means you'll need to use an **if statement**. This is just a bit of code that only runs when a particular condition is true. Like with a `for` loop, an `if` statement's code is in braces (`{}`) following the condition.

--- task ---
First, **delete** the line you wrote earlier to update the heading with your hello message. You're going to need to use the heading for the colours.

Then update your `for` loop to add an `if` statement that checks if you're working with the `answerButton` and, if so, outputs the colours to your heading.

It should look like this:

```JavaScript
for (var i = 0; i < buttons.length; i++) {

  var red = makeColourValue();
  var green = makeColourValue();
  var blue = makeColourValue();

  setButtonColour(buttons[i], red, green, blue);

  if (i === answerButton) {
    heading.innerHTML = `(${red}, ${green}, ${blue})`;
  }
}
```
Notice how you can use `${red}` to include the value of the `red` variable inside your text string.
--- /task ---

Now, you need to check, when the user clicks a button, whether they've clicked the winning button or any other button and let them know if they got the answer right or wrong. To do this you'll need to add an **event listener** to each of the buttons. These tell JavaScript to 'listen' for something to happen, in this case a click on the button, and then run a particular fucntion.

--- task ---
First, before your `for` loop starts, add a line to get the element you're going to use to tell the player if they've won. This is exactly like the way you got the heading a few steps back.

```JavaScript
var answerMessage = document.getElementById('answer');
```
--- /task ---

Finally, inside the `for` loop, add a some code to connect a listener for clicks and give that listener a function to run when it 'hears' one.

--- task ---
This function combines a few things:
 - An `if` statement, although this one includes an `else` afterwards that runs only if the condition is false
 - Using `innerHTML` to update the text of an element on the page
 - The special `this` keyword that means, in this case, 'the button that was clicked'.

```JavaScript
buttons[i].addEventListener('click', function(){
        if (this === buttons[answerButton]) {
            answerMessage.innerHTML = "Correct!";
        } else {
            answerMessage.innerHTML = "Wrong answer! Guess again!";
        }
    });
```
--- /task ---
Now reload the page and play! For now, you'll have to reload the page every time you get it right and want a new colour.