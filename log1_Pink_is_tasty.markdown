---
layout: default
title:  "Oh my god this is Yummy."
num: 2
---

NEED TO ADD: potential pictures, potential inner code, potential part of code to use in the playground.

## 0) Your plate as a canvas


 * Getting your setup done.

```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>

<head>
    <title>p5js Template</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.4.13/p5.js"></script>
    <script>
       
     /*FEEED ME*/ 

    </script>
</head>

<body>
</body>

</html>
```

 * Your first output: 2D visuals. HelloWorld of graphic.
 * Where you place the code: understanding what you're cooking
 * A bit about compiling, hot reloading, and MF sliders

```javascript
        function setup() {
            createCanvas(windowWidth-20, windowHeight-20);
            rect(100,100,100,100);
          }
```

## 1) Show me the goods!
 * learning about 2D shapes
 * comments are fun (and usefull)

```javascript
    // Add in Setup:
    ellipse(300, 300, 100, 50); // How would you make a circle ?
    line(30, 20, 85, 75);
    // Heard of Bezier curves? You can use it too! But it's a secret...

    // Need complexe shape? Ask us, we'll use vertex
```


 * Base of color arrangement.

```javascript
      // Filling the space
      noStroke();
      fill(255,255,0);  rect(100,100,20,20);
      fill(0,255,255);  rect(140,100,20,20);
      fill(255,0,255);  rect(180,100,20,20);

      // Stroke around the space
      stroke(255,0,0);
      fill(0,0,0);       rect(100,140,20,20);
      fill(255,255,255); rect(140,140,20,20);
      fill(0,255,0);     rect(180,140,20,20);

      // Transparency
      noStroke();
      fill(255,255,0, 100);  rect(130,185,20,20);
      fill(0,255,255, 100);  rect(140,180,20,20);
      fill(255,0,255, 100);  rect(150,175,20,20);


      // Vectoriel Vs tint area
      // Know about other coloring space? You can use them too, just ask us.
```

## 2) Static is boring (when a default choice)

 * Not just a static canvas, but a dynamic one

```javascript
    void setup() {
        // bla bla bla
    }

    void draw() {
        fill(255,0,0,3);
        ellipse(300,300,250,250); // Comment / Uncomment this line
    }
```

 * Dynamic is possible, but .. still needs to be done
 * Many ways, rules, generation, interaction....

 * Interaction, variable

```javascript
    ellipse(mouseX, mouseY, 50,50);
```

```javascript
    ellipse(width/2, height/2, mouseX, mouseY);
```

 * Feed non user information, generative (based on data, later, or ... other)

```javascript
    rect(random(width)-25, random(height)-25, 50, 50);
```

    * Draw a lot, add transparency
    * Static/Dynamic, Generatif/Interactive: randomness
    * Position is the default control. Don't forget other parametrs. Try random colors, size....

 * We'll add a lot of possibilities, not all are to be forced (especially not at once!) chosing among your tools will be one hell of a task.

 * Adding the "phase out" when rect(0,0,width,height) with high transparency

## 3) Look at your watch, it's time to be a pro
Yep, already. "Time flies like an arrow. Fruit flies like a banana." Anyway.

    * NoCursor()
    * fullscreen
    * Bam, give me your money

## 4) Even stupid is already a bit intelligent
 * You did already the brain part : connecting the dots. Routing.
 * Routing, good way to test simple stuff. Direct expression.
 * Direct things are too ... direct. Lack poesie, lack the fuzzyness that forces us to interpret and project. We project personal stuff, this is why good fuzzyness will trigger personal projection, and we'll see a personal connexion with the piece.

 *  Guess what? You could stop there. The emphasis should never be too much put on skills. It's never the end game. It's not even the resulting art piece. It's what the spectator will feel. Discovering skills are an amzing way to get inspiration. But never forget that there is a hand that guides all this movement toward creation.


