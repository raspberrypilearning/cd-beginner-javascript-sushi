## Resetting the game

It's not great that you have to reload the page to reset the game, but you can fix that! You can use the reset button that's on the page to reset the game, once you connect a listener to the button and wrap your game code up in a function for that listener to call.

--- task ---
Take the code that needs to run to reset the game — the answer button picker and the `for` loop — and put them in a function called `startGame`, like this:

```JavaScript
function startGame() {

  var answerButton = Math.round(Math.random() * buttons.length);

  for (var i = 0; i < buttons.length; i++) {

    var red = makeColourValue();
    var green = makeColourValue();
    var blue = makeColourValue();

    setButtonColour(buttons[i], red, green, blue);

    if (i === answerButton) {
      heading.innerHTML = `(${red}, ${green}, ${blue})`;
    }

    buttons[i].addEventListener('click', function(){
        if (this === buttons[answerButton]) {
            answerMessage.innerHTML = "Correct!";
        } else {
            answerMessage.innerHTML = "Wrong answer! Guess again!";
        }
    });

  }

}
```
--- /task ---

Reload the page and see what happens now. Nothing seems to be working… why is that? It's because, just like all the other functions you've created, you need to call `startGame` so as your game will, in fact, start.

--- task ---
Add a line at the _very end_ of your program to call the `startGame` function.

```JavaScript
startGame();
```
--- /task ---

Finally, you need to connect a listener on the reset button to `startGame`. You've done this a few times now, so if you want to just try before looking at the instructions, take a shot at it!

--- task ---
Connecting the reset button involves two steps:
 - Select the button using its `id` of 'reset'
 - Attach a click listener to the button that will run the `startGame` function when it's clicked

Add this line to the the end of your program to do that:
```JavaScript
document.getElementById('resetButton').addEventListener('click', startGame);
```
Also, notice how, because you don't need the button again, this time the code skips the step of storing the button in a variable and just directly attaches the listener to the selected button.
--- /task ---

Now check out your game! Once you've gotten the right answer click the reset button and check everything works like it should.