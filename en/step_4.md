## Better song listings

Anyone checking out your music page will get quite confused if you're listing songs with the same title, or with cover versions recorded by different artists. So, you need to add more information to the song listing. Specifically, the name of the artist. When you're creating the song listings, you're using the `displaySongsList()` **function**. I wrote that function and you can find it in the `functions.js` file. It looks like this:

```javascript
  function displaySongsList (songsList) {
    
    var wrapper = document.getElementById ('jsSpace')
    
    var songsListDisplay = document.createElement ('ul')
    
    var song = songsList[0]
    
    songsListDisplay.appendChild(buildSongDisplay(song))
    
    wrapper.appendChild(songsListDisplay)
  }
```
  
+ The version in the file has some notes on what each line is doing, but the one to care about, right now, is this one:
  
```javascript
  songsListDisplay.appendChild(buildSongDisplay(song))
```
  
There's a lot happening here, with **functions** inside **functions**. The **comments** in the file are worth reading to understand it. I could just append a piece of text, but I wanted to use some fancier HTML and add some values from the song, so I wrote another **function** called `buildSongDisplay()`. It's at the very top of the file and right now just looks like this:

```javascript
  function buildSongDisplay (song) {
    var songDisplay = document.createElement ('li')
    var songInfo = '<strong>' + song.title + ' </strong> &#9658;'
    songDisplay.innerHTML = songInfo
    songDisplay.classList.add ('songListItem')
    songDisplay.dataset.songId = song.id
    return songDisplay
  }
```

+ The important lines, for you, are the ones that tell the page what goes inside that `li`. 

```javascript
  var songInfo = '<strong>' + song.title + ' </strong> &#9658;'
  songDisplay.innerHTML = songInfo
```

The first line creates a variable and stores text in it, including `song.title`, which is a **property** of the `song` **variable** that gets **passed** into the **function**. The second line puts it inside the `li`. You want to change the second line to add the artist. 

+ First, to add the word “by”, you'll need to change that first line like this:

```javascript
  var songInfo = '<strong>' + song.title + ' </strong> by &#9658;'
```

+ Now save the change and go back to the `music.html` page. Let it reload and see the difference. You can add any text you like in there. 

+ The weird set of symbols and numbers at the end (`&#9658;`) gives you the play arrow. Try another four numbers and see what you get. Change it back afterwards though! 

+ Go back to `functions.js` and change the line a little more, to look up the artist **property** of the song, like this:

```javascript
  var songInfo = '<strong>' + song.title + ' </strong> by '+ song.artist +'&#9658;'
```

+ Notice that you need to leave the single quotes (`'`) and use a plus either side of the **variable** (**properties** are a particular kind of **variable**) name.
  
+ Re-load the `music.html` page again and check it out.

+ There are a few more **properties** on the song that you can use. Update the `buildSongDisplay()` **function** to display one or two more of them:
  * **genre**—the kind of music e.g. pop, rock, dance, etc.
  * **releaseDate**—when the song was released
  * **length**—how long the full song is
  
+ If you've done the Beginner HTML Sushi Cards, or know HTML some other way, try some other tags in here too! Maybe add a class to the `<strong>` and play with the CSS!

+ Now check out your changes in `music.html` again!