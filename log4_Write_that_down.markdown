---
layout: default
title:  "Food for thought"
num: 5
---

## 1) This course is made with words

 * Powerful medium to share, graphicaly and semanticaly

```javascript
text("word", 10, 30);
```

 * Formating
```javascript
textSize(12);
textStyle(NORMAL); // BOLD, ITALIC
texAlign(CENTER); //LEFT, RIGHTo
textWidth(32);
```

 * Fonts

Can use a lot by default (all on your system), can load them online too. Ask us.

 * randomText
    Array + Random index (float -> int)

 * Moving text

```javascript
    var part;
      
    function setup() {
      createCanvas(windowWidth-20, windowHeight-20);
        background(0);
      part = {};
      part.x = random(100000);
      part.y = random(100000);
    }

    function draw() {
      noStroke();
      fill(255,40);
      part.x+=0.01; part.y+=0.01;
      textFont("Verdana", 30);
      text("Here",  noise(part.x+10)*width,noise(part.y+10)*height);  
    }     
```

 * Explosions
 * Same than natural system. Just ... Start at the right position, and then apply random forces


## 2) Feed on the web
  * Input    - data from the web 
  * noise (perlin, for .. err ... drawing?)

 * concatenation/split
 * Manipulation possible on words
    LoadJSon/httpGet
    JSON
