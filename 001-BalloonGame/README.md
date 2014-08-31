# Random Balloon Game

The best thing about blowing up balloons is that you never know when the balloon will blow up, well this game will test your blowing limits and nerves. 

## 1 start by creating a blank web page with a title

Save the page as __index.html__ and store it on your Desktop

Here you are adding 
* html tag
* head tag
* title tag - which text appears in the browser header

````html
<html>
	<head>
		<title>CoderDojo Random Balloon Game</title>
	</head>
<html>

````

### See what you created

Open __index.html__ in your browser like __Chrome__

__NOW HIT REFRESH IN YOUR BROWSER__ - what do your see?

## 2 Add the web page body take with all the content you want to appear on the screen

The body tag is the most important on  your webpage, 

````html
<html>
	//1 start by creating a blank web page with a title
	<head>
		<title>CoderDojo Random Balloon Game</title>
	</head>
	//2 Add the web page body take with all the content you want to appear on the screen
	<body onload="setup()">
		<div id="gameDiv">
			<div class="topPanel">
				<div id="heading">Random Balloon Game</div>
				<div class="score">
					<div class="scoreTitle">SCORE</div>
					<div id="score">0</div>
				</div>	
			</div>
			<div id="balloon" onclick="blow()">
				<img src="balloon.png" id="balloonimg"/>
			</div>
			<div id="boom">
				BOOM
			</div>
			<div id="logo">
				<img src="coderdojologo.png"/>
			</div>
			<div class="tieit" onclick="tieit()">tie balloon</div>
		</div>
	</body>
</html>

````

### See what you created

Open __index.html__ in your browser like __Chrome__

__NOW HIT REFRESH IN YOUR BROWSER__ - what do your see?


### What do you think?

The webpage does not look great right, its time to see a new web language called __CSS__ this language adds colours and layout to webpages.  In CoderDojo was way it add cool to your website.

## 3 Add style to your game

The style tag allows you add __CSS__ to your webpage.  To add CSS to a tag, this can be done in 3 ways
* tag name - like __body__ is used to style everything inside the this tag, like background color
* #gameDiv - if you see __#__ in your CSS, then its looking for a tag with an __id__ set with the word (gameDiv) after the __#__ hash.
* .

````html
<html>
	//1 start by creating a blank web page with a title
	<head>
		<title>CoderDojo Random Balloon Game</title>
	</head>
	//2 Add the web page body take with all the content you want to appear on the screen
	<body onload="setup()">
		<div id="gameDiv">
			<div class="topPanel">
				<div id="heading">Random Balloon Game</div>
				<div class="score">
					<div class="scoreTitle">SCORE</div>
					<div id="score">0</div>
				</div>	
			</div>
			<div id="balloon" onclick="blow()">
				<img src="balloon.png" id="balloonimg"/>
			</div>
			<div id="boom">
				BOOM
			</div>
			<div id="logo">
				<img src="coderdojologo.png"/>
			</div>
			<div class="tieit" onclick="tieit()">tie balloon</div>
		</div>
	</body>
	//3 Add style to your game
	<style>
			body {
				background: #F4F6B7;
				padding-left: 10%;
				padding-right: 10%;
				margin-bottom: 0px;
				margin-top: 0px;
				height:100%;
				font-family: Comic Sans MS;
				color: #fff;
			}

			#gameDiv {
				margin-left: auto;
				margin-right: auto;
				margin-top: 0px;
				width: 100%;
				height: 100%;
				background: #7BADEC;
				border-image:url(cd-border.png) 0 100% repeat;
				border-width: 20px;
				border-top: 0px;
				border-bottom: 0px;
			}

			#logo {
				margin: 30px;
				position: absolute; 
				bottom: 0px;
			}

			#balloonimg {
				width: 100%;
			}

			#balloon {
				margin-left: auto;
				margin-right: auto;
				width: 5%;
				cursor: pointer;

			}

			#boom {
				font-size: 150px;
				color: #E60A15;
				text-align: center;
			}

			.score {
				margin: 30px;
				float: right;
				border: 5px solid #6c5529;
				height: 120px;
				width: 250px;
				box-shadow: 8px 8px 5px #6c5529;
				background: #17412F;
				text-align: center;
			}

			.scoreTitle {
				font-size: 30px;
			}

			#score {
				font-size: 60px;
			}

			#heading {
				margin: 30px;
				color: #E60A15;
				font-size: 60px;
				float: left;
				text-align: center;
			}

			.topPanel {
				width: 100%;
				float: left;
			}

			.tieit {
				border: 5px solid #000;
				padding-top: 5px;
				height: 60px;
				width: 200px;
				box-shadow: 8px 8px 5px #000;
				background: #E60A15;
				text-align: center;
				position: absolute;
				font-size: 30px;
				bottom: 20px;
				right: 12%;
				cursor: pointer;
			}
	</style>
</html>

````

## 4 Add the game code

JavaScript adds movement and fun to your website, it enables you move and change pictures and text on your screen.  All games are about changing what you see you on the screen as you play the game.   This is an excellent introduction to game development.

In this game we have 3 main concepts 

* __variables__ - __var__ is something we need to store a value against and change, and excellent example is __var score__ as the score will need to change every time you blow the balloon
* __function__ - provides the action to your game, with __function blow()__ being a great example which blows the balloon up by making the image bigger.
* __if/else__  - allows you make decisions in your game, a good example of have your blown up the balloon? is handled by __if(maxblow > blowcount)__ which checks if the number of blows has exceed the max allowed blow.

````html
<html>
	//1 start by creating a blank web page with a title
	<head>
		<title>CoderDojo Random Balloon Game</title>
	</head>
	//2 Add the web page body take with all the content you want to appear on the screen
	<body onload="setup()">
		<div id="gameDiv">
			<div class="topPanel">
				<div id="heading">Random Balloon Game</div>
				<div class="score">
					<div class="scoreTitle">SCORE</div>
					<div id="score">0</div>
				</div>	
			</div>
			<div id="balloon" onclick="blow()">
				<img src="balloon.png" id="balloonimg"/>
			</div>
			<div id="boom">
				BOOM
			</div>
			<div id="logo">
				<img src="coderdojologo.png"/>
			</div>
			<div class="tieit" onclick="tieit()">tie balloon</div>
		</div>
	</body>
	//3 Add style to your game
	<style>
			body {
				background: #F4F6B7;
				padding-left: 10%;
				padding-right: 10%;
				margin-bottom: 0px;
				margin-top: 0px;
				height:100%;
				font-family: Comic Sans MS;
				color: #fff;
			}

			#gameDiv {
				margin-left: auto;
				margin-right: auto;
				margin-top: 0px;
				width: 100%;
				height: 100%;
				background: #7BADEC;
				border-image:url(cd-border.png) 0 100% repeat;
				border-width: 20px;
				border-top: 0px;
				border-bottom: 0px;
			}

			#logo {
				margin: 30px;
				position: absolute; 
				bottom: 0px;
			}

			img#balloonimg {
				width: 100%;
			}

			#balloon {
				margin-left: auto;
				margin-right: auto;
				width: 5%;
				cursor: pointer;

			}

			#boom {
				font-size: 150px;
				color: #E60A15;
				text-align: center;
			}

			.score {
				margin: 30px;
				float: right;
				border: 5px solid #6c5529;
				height: 120px;
				width: 250px;
				box-shadow: 8px 8px 5px #6c5529;
				background: #17412F;
				text-align: center;
			}

			.scoreTitle {
				font-size: 30px;
			}

			#score {
				font-size: 60px;
			}

			#heading {
				margin: 30px;
				color: #E60A15;
				font-size: 60px;
				float: left;
				text-align: center;
			}

			.topPanel {
				width: 100%;
				float: left;
			}

			.tieit {
				border: 5px solid #000;
				padding-top: 5px;
				height: 60px;
				width: 200px;
				box-shadow: 8px 8px 5px #000;
				background: #E60A15;
				text-align: center;
				position: absolute;
				font-size: 30px;
				bottom: 20px;
				right: 12%;
				cursor: pointer;
			}
	</style>
	//4 Add the game code
	<script src="http://code.jquery.com/jquery.js"></script>
	<script>
		var blowcount;
		var maxblow;
		var score = 10;

		function blow() {
			if(maxblow > blowcount) {
				blowcount = blowcount +1;
				var newWidth = blowcount * 5;
				score = score * 2;
				$("#balloon").width(newWidth+"%");
				$("#score").html(score);
			} else {
				blowup();
			}
		}

		function blowup() {
			$("#score").html(0);
			$("#balloon").hide();
			$("#boom").show();
			score = 10;
			setTimeout(setup, 2000);
		}

		function setup() {
			blowcount=1;
			maxblow = Math.floor((Math.random() * 4) + 1);
			$("#balloon").show();
			$("#boom").hide();
			$("#balloon").width("5%");
		}

		function tieit() {
			if(maxblow == blowcount) {
				setup();
			} else {
				blowup();
			}	
		}
	</script>
</html>
````

## Enjoy

Well done you have developed your first game and are on your way to becoming a computer game ninja.  

