var car,  wall;
var speed, weight;
var deformation;

function setup() {
  createCanvas(1600,400);
  createSprite(400, 200, 50, 50);
  background(255,255,255);
  //background('yellow');
  
  speed=random(55, 90);
  weight= random(400, 1500);
  car= createSprite(50, 200,  50, 50);
  wall= createSprite(1300, 200, 60, height/2);   
  car.velocityX=speed;
  wall.shapeColor='lightblue';
  car.shapeColor='pink';
  deformation=0;

}
function draw(){
  if(wall.x-car.x<car.width/2+wall.width/2 && car.x-wall.x<car.width/2+wall.width/2)
  { car.velocityX=0;
    deformation=(0.5*weight*speed*speed)/22500;
    text(deformation,1050,50);
  if(deformation >180)
   { 
      car.shapeColor="Red";
   }
  if(deformation>100 && deformation<180)
   {
      car.shapeColor="yellow";
   }
  if(deformation<100)
  {
    car.shapeColor="green";
  }
}
drawSprites();
}
