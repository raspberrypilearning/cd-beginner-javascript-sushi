## Getting started

Go to [dojo.soy/js-colours](http://dojo.soy/js-colours). You will see a box containing an example website project. On the right hand side is the website, and on the left hand side is the code that makes the website.

![Trinket showing code and output of code side-by-side](images/tktStart.png)

If you have an account on Trinket, click the **Remix** button at the top right of the project \(if you are not signed in, you will be prompted to do so. Once you've signed in you will then need to click the **Remix** button again\). This creates a copy of the project for you to work with. 

![Remix button](images/tktRemixButtonArrow.png)

It should say "remixed" after you click it
  
![Button now says "remixed"](images/tktRemixedSmall.png)

--- collapse ---
---
title: Using Trinket without creating an account
---

If you don't have an account on Trinket, you can save your work by using one of the options in the **Share** menu. You will get a link that you can either store somewhere, for example, in a document or send to someone via email.
Note: each time you make a change, you will get a new link.

--- /collapse ---

--- collapse ---
---
title: Creating a free account on Trinket
---

You don't have to have an account on Trinket to work with these cards.
However, having one allows you to access your work easily from any computer. It also allows you to save a copy of a project somebody else has shared with you so you can make your own changes to it!

+ Go to [dojo.soy/trinket](http://dojo.soy/trinket) and click **Sign Up For Your Free Account** if you do not already have an account. You will need an email address to sign up. 

+ Enter your email address and choose a password, or ask somebody to do this for you.

+ You can now access all your saved or remixed projects by clicking on your username and going to **My Trinkets**.

!["My Trinkets" menu item](images/MyTrinketsMenuWide.png)

--- /collapse ---

You now have three files:
 - `index.html` is the HTML code for the web page and the page you'll be viewing to check on your work, but you won't actually need to change it.
 - `style.css` is the CSS code that controls what the page looks like. Again, you won't need to change this.
 - `script.js` is where you'll be writing all your JavaScript code.

### Using JavaScript to change a webpage

JavaScript is used all over the internet — from Amazon to YouTube — because it is the best way to make your web pages respond to something the user does. This could be as simple as having a Twitter feed on a homepage, all the way through to live chat and in-browser games. All the coders who built those websites started by figuring out how to do one simple thing: pick part of a web page, and change it. You're going to start in the same place.

The basic structure of a web page is in the HTML code. It's made up **tags**, also called **elements**, that tell the browser what to include when building the page. Some of the HTML for the web page you'll be working with (`index.html`) looks like this:

```HTML
<h1>Guess the colour!</h1>
<h2 id="colourValue"></h2>
<div id="buttonWrapper">
    <button class="colourButton"></button>
    <button class="colourButton"></button>    
    <button class="colourButton"></button>    
    <button class="colourButton"></button>    
    <button class="colourButton"></button>    
    <button class="colourButton"></button>    
</div>
<h2 id="answer"></h2>
```

The `<h1>` and `<h2>` tags are **headings**, they appear on the page as big bold text. Try changing 'Guess the colour!' to something else to see how they work. The `<button>` tags are, as you might have guessed, buttons, although in this case those buttons have been turned into red circles. You'll also see **attributes** in the tags, like `id`, which is a unique identifier for a tag across the whole page, and `class` which is used to identifiy similar tags, like all those `colourButtons`!

The first thing you need to do is select part of the web page using your JavaScript in `script.js`. You will want to use this selection after you've made it, so you need to store it in a **variable**. You can think of a variable as a box for storing things. It has a label (the variable's name) on the outside and you can use that label to get the box later and look at, or change, the thing in it.

--- task ---
Open `script.js` and add these line of code to: 
 - create a variable called `heading`
 - select the item on the page with an `id` of `colourValue` (this has already been given to a heading on the page) and store it in the `heading` variable

```JavaScript
var heading;
heading = document.getElementById('colourValue');
```
--- /task ---

Great! Now you have a piece of the web page that's in your JavaScript so you can change it. You'll use it later as part of the game you build, but for now just make it say hello!

--- task ---
Below where you stored the element from the page in `heading`, add a line that changes the contents of that element like this:

```JavaScript
heading.innerHTML = 'Hello world!';
```
--- /task ---
