---
layout: default
title:  "Brain-plosion"
num: 1
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

  * b) constrained by your brain
    variable, evolution

## 3) Press that button
  * Arcade buttons, mother of most interactions. It's child: the keyboard.
  * It's other child: all devices that are felt as one: foot pedal, makey makey...)
  * Use them. Like, now.

if/then, keyPressed, keycodes
