# Bouncing DVD Logo

If you miss your old DVD Logo days, then this is for you

## HTML Code: 

```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
	<meta http-equiv="X-UA-Compatible" content="IE=edge">
	<meta name="viewport" content="width=device-width, initial-scale=1">

	<title>DVD Logo</title>

	<script src="libraries/p5.js"></script>
	<script src="libraries/p5.dom.js"></script>
	<script src="libraries/p5.sound.js"></script>
	<script src="sketch.js"></script>

	<style>
		body {
			margin:0;
			padding:0;
			overflow: hidden;
		}
		canvas {
			margin:auto;
		}
	</style>
</head>
<body>
</body>
</html>
```

## JavaScript Code: 

```javascript
let x;
let y;

let xspeed;
let yspeed;

let dvd;

let r, g, b;

function preload() {
  dvd = loadImage('dvd_logo.png');
}

function setup() {
  createCanvas(windowWidth, windowHeight);
  x = random(width);
  y = random(height);
  xspeed = 5;
  yspeed = 5;
  pickColor();
}

function pickColor() {
  r = random(100, 256);
  g = random(100, 256);
  b = random(100, 256);
}

function draw() {
  background(0);
  // rect(x, y, 80, 60);
  // Draw the DVD logo
  tint(r, g, b);
  image(dvd, x, y);

  x = x + xspeed;
  y = y + yspeed;

  if (x + dvd.width >= width) {
    xspeed = -xspeed;
    x = width - dvd.width;
    pickColor();
  } else if (x <= 0) {
    xspeed = -xspeed;
    x = 0;
    pickColor();
  }

  if (y + dvd.height >= height) {
    yspeed = -yspeed;
    y = height - dvd.height;
    pickColor();
  } else if (y <= 0) {
    yspeed = -yspeed;
    y = 0;
    pickColor();
  }
}
```

<hr>

`License`: `MIT`
<br>
`Author`: `Abhyuday Tripathi`
<br>
`Language`: `JavaScript`
<br>
`Frameworks`: `Yes, p5.js`
<br>
`Open-Source`: `Yes, MIT License`
<br>