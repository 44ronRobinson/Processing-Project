boolean lefty;
boolean righty;  //  These two booleans serve as falsesafes to ensure that misclicks don't break the loop of the code. 
Projectile projectile;  //  This is a class "Projectile" with object "Projectile."
ArrayList < Projectile > chad = new ArrayList < Projectile >();  //  An ArrayList of Projectile Objects, which stores the potentially infinite list of Objects we create and manipulate
int chaddette;

void setup()  {
  print("Welcome to Group Chad's demonstration of projectile motion using four different objects. To initiate the program, left click the mouse. After that, right click the mouse when you're ready to fire an object. Once the object leaves the window, left click again to start the process over.");
  size(1000, 600);
  projectile = new Projectile();
  chaddette = 0;
  lefty = true;
  righty = false;
}
void draw()  {
  background(#07676A);
  for(Projectile part: chad)  {
    part.update();
    part.checkEdges();
    part.display();
  }
  if ((mousePressed == true)  &&  (mouseButton == LEFT)  &&  (lefty == true)) {  //  Upon pressing the left mouse, the program creates a new object from our array.
   lefty = false;
   righty = true;
    chad.add(new Projectile());
   delay(500);
  }
  if ((mouseButton == RIGHT)  &&  (mousePressed == true)  &&  (righty == true)) {  //  Upon pressing the right mouse, the program retrieves one of those previously created objets. 
    righty = false;
    lefty = true;
    chad.get(chad.size()-1).kick();
    if (chaddette == chad.size())  {
      chaddette = chaddette + 1;
    }
  }
}
class Projectile  {
  PVector location;
  PVector size;
  PVector velocity;
  PVector acceleration;
  PVector gravity;
  float r = random(1, 3);
  float s = random(0, 4);
  
  Projectile()  {
    location = new PVector(width/5, height - width/8);
    size = new PVector(width/8, width/8);
    velocity = new PVector(0, 0);
    acceleration = new PVector(0, 0);
    gravity = new PVector(0, 0);
    s = random(0,4);
  }
  void kick()  {  //  This function essentially fires the shape, initiating its velocity and causing it to move up and forward.
    if (mouseButton == RIGHT)  {
      location.set(width/5, height - (width/8));
      velocity.set(0, r);
      acceleration.set(-.35, 1.8);
      gravity.set(-.0052, .098);
      size.set(width/8, width/8);
    }
  }
  void update()  {
    acceleration.sub(gravity);
    velocity.add(acceleration);
    location.sub(velocity);
  }
  void display()  {  //  The s value dictates the shape that appears in the window. If it falls above and below certain numbers within 0 to 4, then one of four shapes shown here will appear.
    s = s * 1;
    if ((s > 0)  &&  (s < 1))  {
      stroke(#26C1EA);
      fill(#26C1EA);
      ellipse(location.x, location.y, size.x, size.x);
    } else if((s > 1)  &&  (s < 2))  {
      stroke(#26C1EA);
      fill(#26C1EA);
      rect(location.x, location.y, size.x, size.x, 20);
    } else if((s > 2)  &&  (s < 3))  {
      stroke(#26C1EA);
      fill(#26C1EA);
      ellipse(location.x, location.y, 2 * size.x, size.x);
    } else if((s > 3)  &&  (s < 4))  {
      stroke(#26C1EA);
      fill(#26C1EA);
      rect(location.x, location.y, 2 * size.x, size.x, 20);
    }
  }
  void checkEdges()  {  //  This is a bounce affect. It reverses the velocity of each projectile whenever it hits the bottom of the window.
    if(location.y + (size.y/2) > height)  {
      velocity.y = velocity.y * -1;
      gravity.y = gravity.y * 1;
      acceleration.y = acceleration.y * 1;
    }
  }
}
