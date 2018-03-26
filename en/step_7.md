## Cleaning things up

You're almost done, but some of that code you started out with is a little messy. Now that you understand more of how **functions** work, you can clean it all up. You're going to create a pair of **functions** to replace all the code in the `my-script.js` file. 

+ First, make a function called `loadSongsToPage ()` and cut and paste the three lines inside the nameless \(anonymous\) **function** that's in `whenSongsReadyDo ()` so that your file looks like this:

```javascript
  getSongs('U2', 3)

  function loadSongsToPage (){
    var mySongs = getSongTitlesAndArtists()
    displaySongsList(mySongs)
    setupPlayer()
  }

  whenSongsReadyDo(
    function(){

    }
  )
```

+ Next, replace the anonymous **function** with your new one, like so:

```javascript
  whenSongsReadyDo(loadSongsToPage)
```

That looks a little neater and is a bit clearer about what's going on. Because the **functions** are well named, you can read what's happening almost like a sentence.

+ Now, wrap everything up in a function called `putMusicOnThePage ()` like this:

```javascript
  function loadSongsToPage (){
  var mySongs = getSongTitlesAndArtists()
  displaySongsList(mySongs)
  setupPlayer()
  }

  function putMusicOnThePage (){
    getSongs('U2', 3)
    whenSongsReadyDo(loadSongsToPage())
  }

  putMusicOnThePage()
```

+ Load the HTML page and check it all still works. It's nice, but you can make it even better. Just add a couple of parameters to your `putMusicOnThePage ()` function for the search query and the number of songs, like so:

```javascript
  function putMusicOnThePage (query, songCount){
    getSongs(query, songCount)
    whenSongsReadyDo(loadSongsToPage)
  }

  putMusicOnThePage('U2', 3)
```

Your code still does the same thing, but now any programmer can come along and use it to put music on the page without needing to worry about exactly how that works. They just write one line and it appears! You've been doing this all along, with your **functions** calling the **functions** we wrote together \(like `displaySongsList ()`\) and calling my **functions**. You didn't need to know how mine worked, you just need to know what to give them and what to expect them to **return**.

That's the real power of **functions** in programing—you break up the pieces so things can happen or change inside one piece \(or one programer's work\) without the other pieces \(or programers\) needing to know or care as long as the same information going into a **function** still leads to the same effects coming out.

This is amazingly powerful and you'll see it in the rest of the Sushi Cards. You'll also be able to do it yourself if you try working with other Ninjas in your Dojo on a project together: You can write your own **functions**, in your own `.js` files and, as long as you've all planned in advance what input should get what output, you should be able to use each other's code by combining them in one HTML file like you did back on the first card in this series!



