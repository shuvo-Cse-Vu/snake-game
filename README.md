Classic Snake Game
==============

This is the classic 8-bit snake game created using HTML5. This game also includes some 8-bit music and sounds while maintaining the old classic fun. Here are some of the features of the game:

1. 8 Bit graphics just like the classic one.
2. Speed of the snake increases as you progress.
1. Classic 8-Bit Retro Music.
2. Easy to lean, hard to master!
1. You can tweet your score and let the world know about your accomplishment. :D

This game has all the features that of a classic Snake game. The only difference is that it is created using HTML5. It will work in all the browsers except IE8 and below but works best in Chrome and Safari. Now talking about the development, the game's logic is pretty simple. To make the snake move, I just had to pop the tail and put it in front of the head. I took this idea from the awesome tutorial on [The Code Player](http://thecodeplayer.com/walkthrough/html5-game-tutorial-make-a-snake-game-using-html5-canvas-jquery). Here's the code segment for the main logic:

<pre class="codeblock">
//Get the position of the head of the snake
var head_x = snake[0].x;
var head_y = snake[0].y;

//Move snake
var tail = snake.pop();
tail.x = head_x;
tail.y = head_y;
snake.unshift(tail);
</pre>

After creating the basic game, I added sounds and music to it. Then created a basic preloader so that all the sounds and music gets loaded before you start the game. The logic for the preloader is also very simple. Here's how I did it.

<pre class="codeblock">
//Preloading audio stuff
var mainMusic = document.getElementById("main_music"),
  	foodMusic = document.getElementById("food"), 
		goMusic = document.getElementById("gameOver");

var files = [mainMusic, foodMusic, goMusic];
var counter = 0;

var start = document.getElementById("start"),
		loading = document.getElementById("loading");

for(var i = 0; i &amp;amp;lt; files.length; i++) {
	var file = files[i];
	file.addEventListener("loadeddata", function() {
		counter++;
		var percent = Math.floor((counter/files.length)*100);
		loading.innerHTML = "Loading " + percent + "%";
		if(percent == 100) showButton();
	});
}

function showButton() {
	start.style.top = "30%";
	loading.style.top = "100%";
}
</pre>

So here, the start button is hidden using CSS and after the loading is finished, it is showed up. Also, the title screen and the game over is created using basic HTML and CSS. 

I have made this game to support any resolution so try it out on your computer or tablet. If you find any bugs, then tell me using the comments. Happy snaking! ;)
