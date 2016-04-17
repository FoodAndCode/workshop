---
layout: default
title:  "Vector Everywhere"
num: 4
---

## 1) A line, a triangle, a sphere... vectors

  * Definition of a vector

A vector is a way to represent information. As itself, it's nothing, it's just a modelisation, a choice, a representation. In short, it's meant to simplify your life. Let's see how it does it.

  * Scalar Vs Vector.

A scalar is a simple value. 1; 3.2; -54. A vector is a container of multiple values: (3,4); (-3, 1, 56, 0, 2). Usually it's linked with space, and hence has either two values (x and y, for positioning on a screen for instance) or three values (x,z,y) for handling 3D graphics. 

  * Scalar 
```javascript
    var x;
    
    function setup() {
        createCanvas(windowWidth-20, windowHeight-20);
        noStroke();
        x = width/2; // Initialisation
    }

    function draw() {
                background(0,0,255);
        x = x + random(-20,20); // Update
                fill(255,255,255);
        rect(x, 100, 40, 40); // Usage
    }
```

    * Vector

```javascript
    var vec;
    
    function setup() {
        createCanvas(windowWidth-20, windowHeight-20);
        noStroke();
        vec = createVector(width/2, height/2);
    }

    function draw() {
        background(0,0,255);
        var vecAdd = createVector(random(-20,20), random(-20,20));
        vec.add(vecAdd);
      
        fill(255,255,255);
        rect(vec.x, vec.y, 40, 40); // Usage
    }
```

  * A lot of subfunctions are here to be used: https://p5js.org/reference/#/p5.Vector


## 2) Natural Behavior

  * Random is a bit too violent, because chose with same chance strong values and soft values. Another random can be "smoother": gaussian random. Basicaly, you chose a center for randomness, and a span: how much you want to focus on the centre, or spread far.

```javascript
        var vecAdd = createVector(randomGaussian(0,3), randomGaussian(0,3));
```


  * Inputs are orders.
  * Natural structures are appeasing and nice to the eye, and as such a good inspiration
    * The physical world's movements are regulated by forces. Would you know they are present or not, your perception of the world and expectations of movement are modeled by them. Hence why it's nice to take them as inspiration, using the same vocabulary and set of rules than natural life.
    * Look mom I'm doing science : Sum of Forces = mass * acceleration. (As true as simple)
  * Previous code was 'ordered' in position, and we see here we should order it in "acceleration". But what exactly is acceleration? First, think of a car... or a stone you'd drop.

  * Speed = what you add in position at each steps. The bigger the speed, the further you'll go.
  * Acceleration = what you add to speed at each steps. The bigger the acceleration, the quicker you'll go.

```javascript
    var vecP, vecS, vecA;
    
    function setup() {
      createCanvas(windowWidth-20, windowHeight-20);
      
      noStroke();
      fill(255,255,255);
      
      vecP = createVector(width/2, height/2);
      vecS = createVector(0,0);
      vecA = createVector(0,0);
    }

    function draw() {
      background(0);

      // We start with no forces
      var sumF = createVector(0,0);
      // We add a random force
      sumF.add( createVector(randomGaussian(0,3)/10,
                             randomGaussian(0,3)/10) );
            
      // Acceleration, we command you!
      vecA = sumF;
      // Set of rules, update
      vecS.add(vecA);
      vecP.add(vecS);

      
      // Usage, ta-dah!
      rect(vecP.x, vecP.y, 40, 40); // Usage
    }     
```


  * Set of rules as instrument of music
  * Easy to compose with, assured of coherency and genericity
  * Easy to upgrade, to tweak with, to work from

  * Let's add different forces!
  * First, we see that our shape gets out of the screen.
  * We can force it back (change speed with "if" on the edges). But that are limit cases, better to keep a coherent system
  * So the answer is a force. That goes toward the center. Goes stronger as you go further.


```javascript
    // Attraction toward the center
    sumF.add( createVector( (width/2-vecP.x)/5000, (height/2-vecP.y)/5000) );
```



  * Basicaly, we created a attraction force toward a dot (like gravitation).
  * We can make the reference dot whichever we want (like ... a mouse :p)

```javascript
    var planet_A;

    planet_A = createVector(random(width/3, 2*width/3),
                              random(height/3, 2*height/3));

    // Planetary attraction
    sumF.add( createVector( (planet_A.x-vecP.x)/2000, (planet_A.y-vecP.y)/2000) );

    ellipse(planet_A.x, planet_A.x, 40, 40);
```
  
  * Try starting with a default speed for planetary like motions :D (and play with transparency, your best friend)


## 3) In search of simplicity

  * To compute is to order, to make generic rules over generic structure
  * We came from scalar to vector. It was easier to handle multiple dimensions
  * It'd be nice to set everything (pos, speed, acc) in one object. Easier to manipulate


```javascript
var part;
      
    function setup() {
      createCanvas(windowWidth-20, windowHeight-20);
        background(0);
      part = {};
      
      noStroke();
      fill(255,255,255, 20); 
      planet_A = createVector(random(width/3, 2*width/3),
                              random(height/3, 2*height/3));
            part.p = createVector(width/4, height/4);
      part.s = createVector(4,0);
      part.a = createVector(0,0);
    }

    function draw() {
     
      // Definition of the forces
      var sumF = createVector(0,0);
      sumF.add( createVector(randomGaussian(0,3)/30,
                             randomGaussian(0,3)/30) );
            sumF.add( createVector( (width/2-part.p.x)/5000, (height/2-part.p.y)/5000) );
            
            
      // Acceleration, we command you!
      part.a = sumF;
      // Set of rules, update
      part.s.add(part.a);
            part.p.add(part.s);
      
      // Usage, ta-dah!
      rect(part.p.x, part.p.y, 40, 40); // Usage
      
    }     
```

## 4) In search of multiplicity

  * Simplify what you have, it gets easier to grow from

```javascript
// Check for array
// Check for "push"
// Check for "foreach"
```
