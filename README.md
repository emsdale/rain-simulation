# rain-simulation
//open array in use
let drops = [];

function setup() {
  createCanvas(400, 400);
  // loop to initialise 100 raindrops
  for (let i = 0; i < 600; i++) {
    drops[i] = {
  // random x/y rain drops position on canvas 
      x: random(width),
      y: random(height),
  //random speed between
      speed: random(3, 7)
      
    }
  }
}
  // background-continuous
function draw() {
  background('#1FCCE2');
  
  for (let i = 0; i < drops.length; i++) {
    //constantly tells it the speed of the drop through the canvas (thats why           its in draw)
    let drop = drops[i];
    drop.y += drop.speed;
    
    // when drop goes below canvas restart above 
    if (drop.y > height) {
      drop.y = random(20, -height);
      drop.x = random(width);
    }
    // raindrop stroke
    
    stroke('#1896CF');
    line(drop.x, drop.y, drop.x, drop.y + 10);
    
      
  }
}
// 📸 Save a png of our canvas whenever we press the key 's'
function keyTyped() {
  if (key == 's') {
    saveCanvas('photo', 'png');
  }
}
