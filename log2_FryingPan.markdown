---
layout: default
title:  "Brain-plosion"
num: 2
---

## 1) The big three of (our) graphic
    * **Vertex**, wireframe, super super duper nice
    * Tint area. super super duper...
    * Both of those are "vectorial graphics"
    * Now: **Pixel** (photo, JPEG...) 

 * What was there before there was anything?
 * Something before setup, preload

```javascript
    function preload() {
        img = loadImage("http://foodandcode.github.io/assets/images/footer_back.png");
    }

    function setup() {
        //bla bla bla
        image(img,0,0,400,200);
    }
```


    * everything you learn one thing can be reuse for the other. It's cooking. Let's mix. There is no food poisining to worry here.

    * Reusing random, and needing transparency

```javascript
    tint(255,255,255,10); // Color, so plays like stroke and fill
    image(img,random(width)-100, random(height)-50, 200, 100);
```
    * Try instead to control it with the mouse.


## 2) Animation
Brain   - Animation (sinus?) (millis())
  * a) constrained by time
    millis(); cos?sin?

  * We get you default example, better using them on top of something else
  * animation without trace: background

```javascrit
    background(0,0,0);
    rect(millis()/1000, millis()/500, 50, 50);
```

```javascrit
    background(0,0,0);
    rect(millis()/1000, millis()/500, 50, 50);
```

 * Remember the dreaded cosinus and sinus?! They are actually pretty fun

```javascript
      rect(width/2 + cos(millis()/100)*100, millis()/10, 50, 50);
```
 
 * the point is to experiment. You don't need to understand something to experiment, tweak and play with it. Even more: by experimenting and playing with it, you will get a better understanding. While understanding is often necessary to reach new height (or giving a less importance to chance on your way there), it's not a requirement to start doing.

```javascript
      rect(width/2 + cos(millis()/100)*100, height/2 + sin(millis()/100)*100, 50, 50);
```

```javascript
      fill(255,0,0,12);
      rect(width/2  + cos(millis()/100)*100 + random(10),
           height/2 + sin(millis()/100)*100 + random(10),
           50, 50); // Yep, you can do that. spaces or return to line are the same
```


  * b) constrained by your brain
  
  * previously the evolution was based on millis. This function would give us a value that would "change" over time, in a coherent and predictable manner: it would rise, and constantly, with time.

  * Same evolution can be redone with more control. For that, we need something that we can control, and make vary. This vessel is called a variable. You already used a few: mouthX, height... Now, it's time to use your own.

```javascript
    var myVar; // Definition

// Where you define your variables defines where you can use it.
// For now, let's keep it here

    function preload() {
        //bla bla
        // Do not use an empty preload function...
    }

    function setup() {
        //bla bla
        myVar = width/2; // Initialisation
    }

    function draw() {
        //bla bla

        background(255,255,255);
        myVar = myVar + random(-5,5); // Update
        rect(myVar, 0, 10, 10); // Usage
    }
```

  * try to do that in 2D
  *  variables offers you more control over what you want to do. For animations, and ... more more things.

  * Fun with math: max, min, map, abs, randomGaussian
!!CODE HERE?!?!

## 3) Press that button
  * Arcade buttons, mother of most interactions. It's child: the keyboard.
  * It's other child: all devices that are felt as one: foot pedal, makey makey...)
  * Use them. Like, now.

  * keyCodes: https://p5js.org/reference/#/p5/keyCode 
```javascript
// NOT WORKING, check disparities between keyPressed and keyTyped
// Check too when actualy this is called. Seems hard to display something from the function


    function keyTyped() {
      
      if (keyCode === LEFT_ARROW) {
        background(255,255,255);
         myVar = 100;
        }
      
      rect(10,10,100,100);
        if (key === 'a') {
            myVar= width/2;
        } else if (key === 'b') {
            fill(255,0,0,200)
        rect(0,0,width, height);
      }
  // uncomment to prevent any default behavior
   return false;
}
```

  * mouseMoved, mousePressed/released, keyReleased...

