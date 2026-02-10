# Assignment-3---Time
``
let meteorX = 650; 
let meteorY = -50; 
let dinoX = 700;   // Initial position of dinosaur
let meteorAngle = 0;


function setup() {
  createCanvas(600, 400);
  angleMode(DEGREES);
}
function draw() {
  background(0, 100, 400); 

  let blink = sin(frameCount * 0.1) * 5; 
  textSize(30 + blink);
  text("✨", 20, 100); 
  text("✨", 400, 50);
  textSize(50 + blink);
  text("✨", 450, 100);

  noStroke();
  fill("#75501A");
  rect(0, 250, 600, 200);

  //Logic script: position controlled by time

  if (frameCount < 80) {
    meteorX -= 5;
    meteorY += 3;
    meteorAngle = 0;        // normal
  } else if (frameCount < 250) {
    if (dinoX > meteorX + 80) {
      dinoX -= 3;
    }
    meteorAngle = 0;        // still normal
  } else {
    meteorX += 5;           // move away (to the right)
    meteorY -= 3;           // move up
    meteorAngle = 180;      // flip 180 when going away
  }


  // emoji
  textSize(80);
  push();
  translate(meteorX, meteorY);
  rotate(meteorAngle);
  text("☄️", 0, 0);
  pop();

  textSize(80);
  text("🦖", dinoX, 260); 

}
