---
layout: default
title:  "Oh my god this is Yummy."
num: 2
---

## 0) Your plate as a canvas
Soooooo, for those that followed, we'll be using web technology. Yay. So yep, an easy way for you to share your mad artz. Anyway, multiple layers are needed on the web, each for a different usage. You might have heard already from a few.

We'll need to define our layout (which will be basically: DRAW EVERYWHEEEEERE), in HTML. First, we'll create a minimal HTML document, then we'll import the javascript we'll want to use, and then .... we'll use it. Later.


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

 * Your first output: 2D visuals.

Simple one: the rectangle, the "HelloWorld" of graphic. What is helloworld? It's what was meant to be the easiest first output of a program. Just the text "hello world". But nowadays, the emphasis is more on graphics, even natively, at the root of the languages. Hence... a rectangle in our case.

 * Where you place the code: understanding what you're cooking.

You will see bits by bits a structure for your code emerge, some block different from each other. The easiest past to salvation (or at least to a better understanding of coding) is to understand the role of each of those blocks, and why you're writing a specific line of code here and not there. Don't blindly copy paste something anywhere. The code matters, where (and when) it's executed matters too.

First, let's define a function. This is merely giving a name to a block of code. P5JS (the library) will expect those functions, and reuse them as it sees fit. The first function we discover is **setup**. It's a way to .... setup your environment. It's called once, and only once, at first. Let's use it to create our display (our canvas), and draw a rectangle.

You'll see below in the javascrit some little stuff between parenthesis. Those are called parameters. Their values are fed to the function which then act upon them. For instance, when you want to create a canvas, you want to know it's size. Same for the rectangle. And the later needs its position too. 

PS: if you were wondering, all code we'll show now will be in between the "script" tags, so instead of the "FEED ME" we used above.

```javascript
        function setup() {
            createCanvas(windowWidth-20, windowHeight-20);
            rect(100,100,100,100);
          }
```

 * Sliders are good for you. Use them.

If you put your cursor on top of a value, you'll see a slider appearing on top of it. You can use it to play with the value. It's fun, it's useful, what's more to ask? Play a bit with the slider to see the impact of each parameters on the functions.


By the way, did you see that windowWidth? That doesn't seem to be a numerical value... but what it is is pretty straight forward. This is a variable. As you could store & name blocks of code (hence it becoming a function), you can store & name values. In the later case, this new thing is called a variable. We'll be defining ours soon.

## 1) Show me the goods!
 * Let's discover more 2D shapes
 * And let's discover what comments are!

```javascript
    // Add in Setup:
    ellipse(300, 300, 100, 50); // How would you make a circle ?
    line(30, 20, 85, 75);
    // Heard of Bezier curves? You can use it too! But it's a secret...

    // Need complexe shape? Ask us :)
```


 * Base of color arrangement.
 
Ever heard of Red Blue Green, the RGB classics? They're back! Whenever you're speaking about colors, you can describe them in four different ways:
 * 1 value : gray level
 * 2 values: gray level, opacity
 * 3 values: Red, Green, Blue
 * 4 values: Red, Green, Blue, opacity

If you know (and prefer) the vocabulary of Hue, Saturation and Value (or luminosity), you can use it too, just ask us (or seek in the reference page).

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
```

## 2) Static is boring (when a default choice)

 * What we have is not just a static canvas, but a dynamic one

You know already about the setup function, and we won't make modification upon it. We'll add another function after the setup one. Another called **draw**. This one is called each time a new frame is drawn on the screen. In other world, it's called repetitively, endlessly. Daunting!


```javascript
    void setup() {
        // bla bla bla
    }

    void draw() {
        fill(255,0,0,3);
        ellipse(300,300,250,250); // Comment / Uncomment this line
    }
```

Ok, we see it to be dynamic but ... we're not really using this dynamic aspect to its full potential... We have many ways to tap on this potential. In any case, for dynamicity, we need something changing, something moving, something that gives in... One way to do so is to add interactivity. Let's control the shapes using the mouse. For that, we'll be using two new variables:

```javascript
    ellipse(mouseX, mouseY, 50,50);
```

```javascript
    ellipse(width/2, height/2, mouseX, mouseY);
```

No way, that simple? Amazing. But ... let's not stop there. While moving around with the cursor was obvious, changing the size wasn't. Try to think of another uncommon interaction usage within already such a simple system.

 * Already tired? You know, interaction is not the only way to add dynamicity...

You can really on non user information. Either some data you'd feed on (music, camera, stream from the web...) or just tap on the beauty of randomness. While randomness alone isn't so great, add to it a few rules to guide it in a direction and you'll be amazed at the result.

Here we go with another superpower: the function random. Feed it a number, and it'll give you one random number between 0 and that number. Feed it two numbers, and it'll give you a random one between those two. Almost magic.

```javascript
    rect(random(width)-25, random(height)-25, 50, 50);
```

 * Crazy gimmick, works every time: Draw a lot with low transparency.
 * Static/Dynamic, Generative/Interactive: randomness
 * Position is the default control. Don't forget other parameters. Try random colors, size....

 * We'll add a lot of possibilities, not all are to be forced (especially not at once!) choosing among your tools will be one hell of a task.

 * What would happen if you add a dark rectangle with low transparency at each step? Whatever else you'd draw there would fad over time. Try it out!

 * If you want only to see what you're drawing at each stept (**which will an important direction later**) then you might want to set the background at each begining of the draw function by calling the background function with a color. Like: **background(0);**


## 3) Look at your watch, it's time to be a pro
Yep, already. *Time flies like an arrow. Fruit flies like a banana.* Anyway.

 * NoCursor(); ==> Hide this ugly cursor I shall not see
 * fullscreen  ==> Hide those status bar I shall not see
 * Bam, give me your money, that I shall see.

## 4) Even stupid is already a bit intelligent
 * You did already the brain part : connecting the dots. Routing. Just routing one entry point (randomness, or mouse) to a display (size, color...)
 * Routing is a good way to test simple stuff. Direct expression.
 * But ... direct things are too ... direct. Lack poesy, lack the fuzzyness that forces us to interpret and project. We project personal stuff, this is why good fuzzyness will trigger personal projection, and we'll see a personal connexion with the piece.

 *  Guess what? You could stop there. The emphasis should never be too much put on skills. It's never the end game. The end game is not even the resulting art piece. It's what the spectator feels. Discovering skills are an amazing way to get inspiration. But never forget that there is a hand that guides all this movement toward creation.


