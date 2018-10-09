## Changing a button's colour
Since the whole game is based on having different coloured buttons, you're going to need a way to change a button's colour! 

Colours on computers are made up of three different values — for red, green, and blue — that are mixed together to form the 16777216 colours that a computer can display. Each value is between 0 and 255. So what you need to be able to do is take those three numbers and tell the button you want to change to use them as its background colour.

Because you will need to do this a few times, you want to teach JavaScript to do most of the work for you, using a **function**.

--- collapse ---
---
title: What is a function?
---
Code is normally made up of functions — sets of instructions joined together with a name. T hink of something like making a cup of tea as a function: 

  1. Get kettle
  2. Put water in kettle
  3. Boil water
  4. Get teapot
  5. Put teabag in teapot
  6. Put water in teapot
  7. Wait...
  8. Get cup
  9. Pour tea into cup
  
That's a lot of steps! Imagine having to tell someone to do each of them every time you wanted them to make tea! It's much easier to teach someone how to make a cup of tea once and then just ask them to 'make tea' in future! It's the same with code: We can use functions to do complex things with simple commands.

--- /collapse ---

--- task ---
Your function needs to be able to:

 - Take a button
 - Take a value for each of red, green, and blue
 - Use those values to make a colour
 - Assign that colour as the background colour of the button

The actual colour change is done by changing the **CSS** style rule for the button.

Add this code to your `script.js` file.
```JavaScript
function setButtonColour(button, red, green, blue){
    button.setAttribute('style',
                        'background-color: rgb('+ red +','+ green +','+ blue +');'
                       );
}
```
--- /task ---

Now, before you can use your function, you need a button to point it to! All the `button` tags in the HTML file you started with have been given the `class` 'colourButton'. You can use this to select them as a group and then choose one to test your function on.

--- task ---
At the start of your `script.js` file, add this line to get all the buttons and store them in a variable called `buttons`:

```JavaScript
var buttons = document.getElementsByClassName('colourButton');
```
--- /task ---

What you've got is called an **array**: a variable that's a list of things, in this case anything with the class `colourButton` on the page. You can read what's in any position of the arry using square brackets `[]` and the position of the item you're looking for. Since JavaScript starts counting from zero, you can get the first item in the array like this:

```JavaScript
buttons[0]
```

--- task ---
Below where you created your `buttons` variable, add this line of code that takes the first button and changes the colour to blue using your `setButtonColour` function:

```JavaScript
setButtonColour(buttons[0], 0, 0, 255);
```
--- /task ---

Now reload the page and check that it changes colour!

--- challenge ---

## Challenge: Pick your own colours

Using your `setButtonColour` function try changing the colour of the button to some of these:
  - Green
  - Purple
  - Yellow

--- hints ---
--- hint ---
Changing the values of `red`, `green`, and `blue` that you pass to `setButtonColour` will change the colour of the button.
--- /hint ---
--- hint ---
Colour values go from `0` to `255`. You're mixing light, not paint, so some of the results might not be what you expect!
--- /hint ---
--- hint ---
Green is one of the three primary colours you're mixing. Purple and yellow can be found by mixing two of the three in equal amounts.
--- /hint ---
--- /hints ---

--- /challenge ---