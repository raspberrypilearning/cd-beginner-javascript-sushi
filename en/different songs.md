1. Now you have the song listing displaying the way you want it to, it's time to make it display some music you want! The very first line in “my-script.js” is `getSongs()`. This **function** calls a **webservice**—a computer on the internet that will respond to a **query** that's correctly formatted with some information in a consistent format. In this case, what comes back is in **json** (JavaScript Object Notation) format, but my code handles most of that so you don't have to worry about it! You'll see it again in the Intermediate and Advanced Sushi though!

2. On the previous card you saw **functions** being **passed** **variables**. These **variables**, called the **parameters** of the **function** are used by the **function** to decide what to do and how. You don't need to change my `getSongs()` to get different songs, you just need to change the **parameters** you **pass** to it. First, go ahead and ask it for some music you'd like better than this song. You can do that by **passing** the name of a song, or an artist, like this:
  ```javascript
    getSongs('U2')
  ```
 or like this:
  ```javascript
    getSongs('Let it go')
  ```
  Plug in a song or band you love, save “my-script.js” and then reload “music.html” and check it out!
  
3. The other **parameter** that `getSongs()` will take is the number of results you want. Right now, you're only seeing one song. So how about adding a few more? When you're **passing** multiple parameters to a **function** you need to separate them with a comma (`,`) like this:
  ```javascript
    getSongs('U2', 3)
 ```
 Notice that the number doesn't get surrounded by quotes (`''`)—you only need to do that for text. In fact, it will usually confuse JavaScript if you wrap a number in quotes! Make the change to fetch 3 songs and save “my-script.js” again.
  
4. Now reload “music.html” and see what happens. 

  Nothing changed, right? That's a bit odd. Do you know why? 

  It's because while you're now getting more than one song in, your code in the `displaySongList ()` **function** from the last card is still only displaying the first song. You'll need to go back and update it to display as many songs as it gets. You'll see how to do that on the next card!
 