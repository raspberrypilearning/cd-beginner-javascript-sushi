## Your first JavaScript

JavaScript code is normally made up of **functions**: sets of instructions joined together with a name. Think of something like making a cup of tea as a **function**: 

  1. Get kettle
  2. Put water in kettle
  3. Boil water
  4. Get teapot
  5. Put teabag in teapot
  6. Put water in  teapot
  7. Wait...
  8. Get cup
  9. Pour tea into cup
  
That's a lot of steps! It's much easier to teach someone how to make a cup of tea once and then just ask them to do that in future! It's the same with JavaScript. We use functions to do sometimes pretty complex things with simple commands. The great thing is that **you** don't have to write the function to use it. So to start with, use a few of mine by updating your `my-script.js` file to look like this:

```javascript
  getSongs()
  
  whenSongsReadyDo(
    function(){
      var mySongs = getSongTitlesAndArtists()
      displaySongsList(mySongs)
      setupPlayer()
    }
  )
```

What's happening here is your code asks the internet for some songs with `getSongs()`. Then it checks if the songs have arrived yet with `whenSongsReadyDo()` and, once they've arrived, runs the **function** inside it, which is the rest of the code for your program.
That code does three things:
  * It gets a list of songs and stores them in a container, which we call a **variable** called “mySongs”.
  * It gives the list in “mySongs” to a function that displays them by creating some HTML
  * It creates a music player and sets it to react to clicks on the songs

+ Now switch to the `index.html` file and look at the preview window. You'll see that there's a song title there—“Yesterday”—and a play button. If you click the button, the song will play. This is great, but it's not a lot of use for a few reasons. You're going to fix them on the next few cards:
  * First, “Yesterday” is one of the most recorded songs in history and there's no way of telling whose version this is!
  * Second, it only shows one song, even though there are lots of versions of “Yesterday”
  * Third, you probably want to have cooler music on your webpage, so you'll need to search for something else!
  
  Time for you to improve on my **function**!