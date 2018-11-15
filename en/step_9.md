## Challenge: Fill the page with the winning colour

Now that you've built your game, here's a challenge for you: Using what you've learned, can you fill the page will the winning colour when the player chooses it correctly? 

You'll need to know two new things to manage this. First, the whole of the page is contained in the `body` tag of the HTML file. Second, just like you can select by `id` and by `class`, you can select by `tagName`. Just like classes, there can be more than one result (although, in the case of the `body` tag, there will only ever be one), so you'll get an `array` back.

So, using `document.getElementsByTagName()` can you change the background of the page to the winning colour when the player chooses it correctly?

--- hints ---
--- hint ---
Remember how you changed the colour of a button? You can use the same function to change the body's background colour.
--- /hint ---
--- hint ---
Update the background colour at the same time as updating the message to the user telling them they've won.
--- /hint ---
--- /hints ---