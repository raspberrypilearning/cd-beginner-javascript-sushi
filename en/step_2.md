## Using JavaScript to change a webpage

JavaScript is used all over the internet — from Amazon to YouTube — because it is the best way to make your web pages respond to something the user does, or change after they've been downloaded. This could be as simple as having a Twitter feed on a homepage, all the way through to live chat and in-browser games. All the coders who built those websites started by figuring out how to do one simple thing: pick part of a web page, and change it. You're going to start in the same place.

The first thing you need to do is select part of the web page (`index.html`) using your JavaScript in `script.js`. You will want to use this selection after you've made it, so you need to store it in a **variable**. You can think of a variable as a box for storing things. It has a label (the variable's name) on the outside and you can use that label to get the box later and look at, or change, the thing in it.

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
