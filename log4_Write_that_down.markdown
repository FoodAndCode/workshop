---
layout: default
title:  "Food for thought"
num: 5
---

## 1) This course is made with words

 * Powerful medium to share, graphicaly and semanticaly

text("word", 10, 30);

 * Formating
textSize(12);
textStyle(NORMAL); // BOLD, ITALIC
texAlign(CENTER); //LEFT, RIGHTo
textWidth("???")


 * Fonts

var fontRegular, fontItalic, fontBold;
function preload() {
   fontRegular = loadFont("assets/Regular.otf");
   fontItalic = loadFont("assets/Italic.ttf");
   fontBold = loadFont("assets/Bold.ttf");
}
function setup() {
   background(210);
   fill(0).strokeWeight(0).textSize(10);
   textFont(fontRegular);
   text("Font Style Normal", 10, 30);
   textFont(fontItalic);
   text("Font Style Italic", 10, 50);
   textFont(fontBold);
   text("Font Style Bold", 10, 70);
}

 * randomText

 * Moving text

 * Explosions

 * concatenation/split

## 2) Feed on the web
    * Input    - data from the web + more random.

    for each, array, LoadJSon/httpGet
    JSON
