---
layout: default
title:  "Brain-plosion"
num: 3
---

## 1) The big three of (our current) graphic vocabulary
 * Using Strokes: **Vertex**, wireframe, super super duper nice
 * Using Fill: **Tint area**. super super duper...
 * Both of could be sum up as "vectorial graphics"
 * Now: **Pixel** (photo, JPEG...)

If you're asking yourself "what was there before there was anything?", we have an answer. Before anything, there was the **preload** function, used to not just load, but preload. Who would have guessed. Loading before the setup what you'll need later, like images.

Images are like rectangles. Once defined, you display them using the **image** function, feeding it positions and size.

Oupsy, while we'll discuss variables a bit more in depth later, we'll be already using them now. In the code below, *img* is a variable. A name, a container, that has some complexe values (which describe the image linked). What we're doing here is a bit of a shortcut, we'll see later why.

```javascript
    function preload() {
        img = loadImage("http://foodandcode.github.io/assets/images/footer_back.png");
    }

    function setup() {
        //bla bla bla
        image(img,0,0,400,200);
    }
```


 * Don't forget that everything you learn on one thing can (should) be used on another. It's cooking. Let's mix. There is no food poisining to worry here.

 * Wondering how to apply the vocabulary of color to a picture? Wonder no more.

For that we use the function **tint**. You can feed it a color as you would with fill, stroke or background.

```javascript
    tint(255,255,255,10); // Color, so plays like stroke and fill
    image(img,random(width)-100, random(height)-50, 200, 100);
```

  * Try instead to control the color with the graphic tablet.


## 2) Animation
Another possible brain. We'll animate our lovely shapes. This animation needs to be described. Two main ways arise:

  * a) constrained by time

We'll defined a movement using time, more precisely the function **millis** which gives us the number of milliseconds ellapsed. Let's divide this because it can gets high pretty quickly, and feed that to the position of a rectangle.

```javascrit
    background(0,0,0);
    rect(millis()/1000, millis()/500, 50, 50);
```

Ok, this is boring. You'd better use that new power on something more fun.


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
  
Previously the evolution was based on time. This function would give us a value that would "change" over time, in a coherent and predictable manner: it would rise, and constantly, with time.

Similar evolution can be redone with more control. For that, we need something that we can control, and make vary. This vessel is called a variable. You already used a few: mouthX, height... Now, it's time to use your own.

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
  * variables offers you more control over what you want to do. For animations, and ... more more things.

## 4) Press that button
  * Arcade buttons, mother of most interactions. Its child: the keyboard.
  * It's other child: all devices that are felt as one: foot pedal, makey makey...)
  * Use them. Like, now.

Another couple of functions, **keyPressed** & **keyTyped** for classic keys and control keys. But among those function, a most important new keyword: **if**. The base of coputation. Thesis could be written on it, its importance, what it means, what it represents. It's the atom of the computational world. What it does is test for something, and do one thing if it's true (and optionaly another if it's false). This is the basic of artificial reasoning. After the if, a condition is tested among parenthesis, and among curly brackets (as with functions), the block of code needed to be executed. If you want to do something when something is not valid, then use *else* as done below. You can test many things with conditions. Equality with *===*, comparison with *<* and *>*... many more that we'll discover another time!

Last: key and keycodes are the value of the key last types. Try it out a bit, it'll make way more sense that way than reading a wall of text.

```javascript
   function keyPressed() {
      if (keyCode === LEFT_ARROW) {
         background(255,random(255), 255);
            //keyCodes: https://p5js.org/reference/#/p5/keyCode 
      }
  }

   function keyTyped() {
      if (key === 'a') {
         background(255,0, 255);
      } else if (key === 'b') {
         background(255,255, 255);
      }

}
```

  * You can check out (or ask us) about other function involoved with the mouse and keyboard:  **mouseMoved**, **mousePressed**, **mouseReleased**, **keyReleased**...

