# patatapClone
This is using howel.js for sounds and animation using page.js, which is 2 libraries used to create this fun project.
<!doctype html>

<html>
	<head>
		<title>Patatap Clone</title>
		<meta charset="UTF-8">
		<meta name="viewport" content="initial-scale=1.0">
        <script type="text/javascript" src="paper-full.js"></script>
        <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/howler/2.0.9/howler.core.min.js"></script>
        <link rel="stylesheet" href="circles.css">
        
        <!-- Load the Paper.js library -->
<script type="text/javascript" src="js/paper.js"></script>
<!-- Define inlined PaperScript associate it with myCanvas -->
<script type="text/paperscript" canvas="myCanvas">

var keyData = {
a: {
  
  sound: new Howl({
   src: ['sounds/bubbles.mp3']
  }),
  color: "purple",
},

s: {
 color: "green",
 sound: new Howl({
  src: ['sounds/clay.mp3']
 })
},

d: {
 color: "yellow",
 sound: new Howl({
  src: ['sounds/confetti.mp3']
 })
},
f: {
  
  sound: new Howl({
   src: ['sounds/dotted-spiral.mp3']
  }),
  color: "purple",
},

g: {
 color: "blue",
 sound: new Howl({
  src: ['sounds/glimmer.mp3']
 })
},

h: {
 color: "red",
 sound: new Howl({
  src: ['sounds/moon.mp3']
 })
},

j: {
 color: "#c2e8e2",
 sound: new Howl({
  src: ['sounds/flash-1.mp3']
 })
},
k: {
  
  sound: new Howl({
   src: ['sounds/flash-2.mp3']
  }),
  color: "#b6475b",
},

l: {
 color: "#d07e59",
 sound: new Howl({
  src: ['sounds/flash-3.mp3']
 })
},

q: {
 color: "#5875ee",
 sound: new Howl({
  src: ['sounds/pinwheel.mp3']
 })
},


w: {
 color: "#a3e815",
 sound: new Howl({
  src: ['sounds/piston-1.mp3']
 })
},
e: {
  
  sound: new Howl({
   src: ['sounds/piston-2.mp3']
  }),
  color: "#2c4866",
},

r: {
 color: "#77f044",
 sound: new Howl({
  src: ['sounds/piston-3.mp3']
 })
},

t: {
 color: "#91adf7",
 sound: new Howl({
  src: ['sounds/prism-1.mp3']
 })
},

y: {
 color: "#d38a66",
 sound: new Howl({
  src: ['sounds/prism-2.mp3']
 })
},


u: {
 color: "#7b012c",
 sound: new Howl({
  src: ['sounds/prism-3.mp3']
 })
},

i: {
  
  sound: new Howl({
   src: ['sounds/splits.mp3']
  }),
  color: "#e60c09",
},

o: {
 color: "#0007c0",
 sound: new Howl({
  src: ['sounds/squiggle.mp3']
 })
},

p: {
 color: "#cb54ba",
 sound: new Howl({
  src: ['sounds/strike.mp3']
 })
},


z: {
 color: "#b8a129",
 sound: new Howl({
  src: ['sounds/suspension.mp3']
 })
},


x: {
 color: "#8dd241",
 sound: new Howl({
  src: ['sounds/timer.mp3']
 })
},

c: {
  
  sound: new Howl({
   src: ['sounds/ufo.mp3']
  }),
  color: "#dd2acd",
},

v: {
 color: "#e9f85e",
 sound: new Howl({
  src: ['sounds/veil.mp3']
 })
},

b: {
 color: "#e086b0",
 sound: new Howl({
  src: ['sounds/zig-zag.mp3']
 })
},

n: {
 color: "#18efbb",
 sound: new Howl({
  src: ['sounds/moon.mp3']
 })
},

m: {
 color: "#8371ad",
 sound: new Howl({
  src: ['sounds/glimmer.mp3']
 })
}


}



var circles = [];


function onKeyDown(event) {
  if(keyData[event.key]){
      var maxPoint = new Point(view.size.width, view.size.height);
    var randomPoint = Point.random();
    var point = maxPoint * randomPoint;
    var newCircle = new Path.Circle(point, 500)
    newCircle.fillColor = keyData[event.key].color; 
    keyData[event.key].sound.play();
	circles.push(newCircle);
  }   
  
}


function onFrame(event){
  for(var i = 0; i < circles.length; i++){
    circles[i].fillColor.hue += 1;
    circles[i].scale(0.9);
   
    }
  }


      
        </script>
      
	</head>
<body>
       
        
      <canvas id="myCanvas" resize></canvas>   
	</body>
</html>
