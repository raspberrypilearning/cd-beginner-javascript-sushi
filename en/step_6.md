## As many songs as you like

Now you need to make the page display more than one song. You can do that by opening up `functions.js` and changing `displaySongList ()` to include a **loop** that repeats the same code until you have no more songs. The kind of **loop** you'll be using is called a **while loop**. It does the same thing over and over while a condition is true. By being clever with **variables**, you can make it display every song on the list. 

+ So, to begin with, make a couple of variables. Add them in just below the line that creates the `ul`, like this:

```javascript
  var songsListDisplay = document.createElement ('ul')

  var songsDisplayed = 0
  var songsToDisplay = songsList.length
```
  
The variables are created using the `var` **keyword**. Every **variable** needs that before its name when it's created. The first **variable**, `songsListDisplay` is just holding a number. It's going to be used as a counter, and it's starting at `0`. JavaScript counts from 0 instead of 1. 
  
The second **variable** is more interesting. It's storing the length of the `songsList`, which is a **property** of the `songsList` you can ask it for. The way this **loop** is going to work, to display every song, is by keeping a count of how many songs it has displayed in `songsDisplayed` and comparing that to `songsToDisplay`. As long as the count is less than (`<`) the target number, it will keep going. 

+ Add the **loop** in below the variables like this

```javascript
  var songsToDisplay = songsList.length

  while(songsDisplayed < songsToDisplay){
    var song = songsList[songsDisplayed]
    songsDisplayed = songsDisplayed + 1
  }
```
 
+ Look at how the `song` **variable** is created every time the **loop** runs. Because it is created in the **loop**, it is destroyed every time the loop ends.

There's a new bit of code there, populating the `song` **variable**: `songsList[songsDisplayed]`. The list of all the songs stored in the `songsList` **variable** is numbered from `0` to `(number of songs in list - 1)` and you can access the information about any song by using the square brackets `[ ]` with the right number in them. By using the value of `songsDisplayed` and changing that value by 1 every time the loop runs, you move one step down the list every pass (called an **iteration**) through the loop.

+ Take a look, too, at how the value of `songsDisplayed` is changed. Notice that we can add one to its current value and then store it back into itself. Also, notice how important the right order of the lines is here. If they were reversed, the first song would never be displayed!
 
+ There's one thing still missing here: The line that actually displays the song! Find these lines after the end of the **loop**:

```javascript
  var song = songsList[0]
  songsListDisplay.appendChild(buildSongDisplay(song))
```
  
+ Delete the first one. You don't need it anymore as you are creating the `song` **variable** inside the **loop**. Cut (`ctrl+x` on Windows, `cmd+x` on a Mac) the second line and paste (`ctrl+v` on Windows, `cmd+v` on a Mac) it as the last line inside your **while loop**.
  
+ Now reload `music.html` and watch all the songs appear! 

  