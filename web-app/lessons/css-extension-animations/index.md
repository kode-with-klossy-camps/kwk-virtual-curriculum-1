---
title: CSS Animations
---

[Back to Lesson Index]({{ site.url }}/web-app/lessons)

## 🎯 Learning Goals

* Write transformations for HTML elements
* Build CSS animations with keyframes
* Try out CodePen

## 📗 Technical Vocabulary

- Animation
- Keyframes
- Transformation

## Overview

CSS has some "behavior tricks" up its sleeve. Through CSS transitions, transformations, and animations you can create quite a bit of movement on your page without any real JavaScript. Check out some of these stunning examples:

- <a target="blank" href="https://www.supremo.co.uk/typeterms/">Type Terms</a>
- <a target="blank" href="https://codepen.io/_fbrz/pen/whxbF?editors=1100#0">Code Pen: Page Flip</a>
- <a target="blank" href="http://demo.marcofolio.net/3d_animation_css3/">Movie Posters</a>
- <a target="blank" href="http://www.romancortes.com/ficheros/css-coke.html">Coke Can</a>

## Transformations

`transform` is a CSS property that can be used to change the way an element is presented. It can take a variety of values. Here are some popular ones:

- `transform: translate(40px, 100px);`
- `transform: scale(4);`
- `transform: rotate(180deg);`

Each of the examples above provides specific values (40px, 100px, 4, and 180deg), but those numbers could change.

<div class="try-it">
  <h2>Try It: Transformations</h2>
  <p>Open up the <a target="blank" href="https://replit.com/@kodewithklossy/css-animations-try-it-transform#style.css">repl.it project</a> demonstrated below, fork it, and play around with these examples. We already have <code class="try-it-code">transform: rotate(90deg);</code> in there right now; what is that property doing?</p>
</div>


<div style="height: 300px;">
  <img src='https://static.boredpanda.com/blog/wp-content/uploads/2016/02/cute-hedgehogs-44__700.jpg' style="height: 300px; transform: rotate(90deg);">
</div>
<br>


## Animations

`animation` is a CSS property that can be used to animate other CSS properties like color, background-color, height, width, and more! The value of the `animation` consists of 3 things: the name, duration, and timing. More can be added, but those 3 are the main things you will use and see.

<div class="try-it">
  <h2>Try It: Transformations</h2>
  <p>Open up the <a target="blank" href="https://replit.com/@kodewithklossy/css-animations-change-me#style.css">repl.it project</a> demonstrated below, fork it, and play around with this animation, as you read through the animation walkthrough below</p>
</div>

<div class="animation-change-me">

</div>
<br>



### Animation Values

Let's break down what's happening with that 3-part value for the `animation` property:

- `change` is the name of the keyframe, or set of directions, for the animation to follow. More on that in the next section
- `5s` is the duration that this animation will occur over. You can change it to `1s` (1 second) and see it speed up, or to something like `15s` (15 seconds) and see it really slow down!
- `infinite` refers to how long we want this animation to continue. Specifically `infinite` will continue, almost on a loop. You can substitute `ease` or `linear` and see what changes. (There are more, less popular options here as well!)

### Keyframes

`@keyframes` are really where the magic happens. In the previous section, we mentioned `change` as the keyframe. Without the `@keyframe` named `change`, the word `change` would just be some undefined variable that CSS would ignore.

`@keyframes` allow us to control the animation each step of the way by defining styles along the animation sequence. In the CodePen above, we had keyframes at 0%, 50%, and 100% - so at the start, half way through, and at the end of the animation duration (the number of seconds you provided), those CSS rules will be true. The code from the CodePen is annotated below:

```css
@keyframes change {               /* the name of the keyframe is "change" */
  0% {                            /* at 0% of the time, so at the start... */
    background-color: #331C82;    /* make the background color #331C82 */
  }

  50% {                           /* at 50% of the time, so halfway through... */
    background-color: #1C8266;    /* make the background color #1C8266 */
  }

  100% {                          /* at 1000% of the time, so at the end... */
    background-color: #331C82;    /* make the background color #331C82 */
  }
}
```

In between the 0% and 50%, and 50% and 100% directions, CSS is smart enough to make that change between those two rules very gradually so it's a smooth transition!

## Building a CSS Ghost

For the rest of this lesson, we will work through building a little bouncing ghost with CSS animations! Eventually, he/she/they will look like this:

<img class="small" src="{{ site.url }}/web-app/lessons/css-extension-animations/assets/ghost-shadow.gif" alt="finished ghost">

Create a new repl.it prject and then we'll start simple. First, let's create a container `div` that we can use to contain all of our ghost parts (body, eyeballs, flaps, etc.). We'll give this container a width of 100px in CSS.

```html
<div class="ghost-container">

</div>
```

```css
.ghost-container {
  width: 100px;
}
```

Now that we have a container, we can add another `div` inside for the basic ghost body. We will style the height and background color of this inner ghost-body element to look like the picture below:

<img class="small" src="{{ site.url }}/web-app/lessons/css-extension-animations/assets/ghost-step-one.png" alt="shapeless ghost">

#### Basic Ghost Shape

Let's use a `border-radius` to create the head of the ghost.

<img class="small" src="{{ site.url }}/web-app/lessons/css-extension-animations/assets/ghost-step-two.png" alt="basic ghost">

#### Ghost with Basic Flaps

Next, we'll add three more `div`s to create flaps. Give these flaps the class of "flap". We'll use CSS to get these divs to line up next to each other. NOTE: This part may take some tinkering, <a target="blank" href="http://gph.is/1c4Sfem">like this</a>.

<img class="small" src="{{ site.url }}/web-app/lessons/css-extension-animations/assets/ghost-step-three.png" alt="basic flaps ghost">

#### Ghost with Curved Flaps

Finally, we'll use the `border-radius` to curve the flaps on the bottom.

<img class="small" src="{{ site.url }}/web-app/lessons/css-extension-animations/assets/ghost-step-four.png" alt="curved flaps ghost">

### Transformations

Add this line to your .ghost-container:

```css
.ghost-container {
  transform: translate(200px, 50px);
}
```

Earlier, we talked about some of the transformations at our disposal. You can also add more than one transformation. For example:

```css
.ghost-container {
  transform: scale(0.3) rotate(-40deg);
}
```

<div class="try-it">
  <h2>Try It: Ghost Transformations</h2>
  <p>Add one or more transformation values to your ghost-container and change the values to see how it changes your ghost.</p>
</div>

#### Animation with Keyframes

Keyframes allow us to define a specific set of styles over the course of a time period. For example, if you said you wanted an animation to last 10 seconds, you could then define what you want the element to do at specific percents through the time period.

There are two parts to this process: First, you must define the keyframes. <a target="blank" href="https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes">Mozilla Keyframes Docs</a>

Then, you need to define the animation property for a specific element. <a target="blank" href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations">Mozilla Animation Docs</a>

This is what they look like when used in conjunction:

```css
.ghost-body {
  animation: camouflage 5s linear infinite;
}

@keyframes camouflage {
  50% {
    background-color: orange;
  }
}
```

### Using Keyframes to Add Horizontal Movement

Can you use what you know about keyframes and the animation property to make your ghost move across the page?

Hint: You'll need to use the `transform: translate()` property. Be sure to add two values for pixels inside of the parentheses.

<img class="small" src="{{ site.url }}/web-app/lessons/css-extension-animations/assets/ghost-simple-move.gif" alt="simple move ghost">

### Multi-directional Moving Ghost

Now, let's get more complicated. Right now, we have one keyframe at 50%. Can you make **several keyframe points** so that the ghost looks like it is floating across the screen while also moving slightly up and down?

<img class="small" src="{{ site.url }}/web-app/lessons/css-extension-animations/assets/ghost-complex-move.gif" alt="multi-directional moving ghost">

### Ghost with Wiggling Flaps

Define another keyframe called `wiggle` and make it so that the `border-radius` on the ghost flaps change in some way at 25% and 75%. Be sure to add `animation: wiggle 3s linear infinite` to your `.flap` rule in CSS.

<img class="small" src="{{ site.url }}/web-app/lessons/css-extension-animations/assets/ghost-wiggle-flaps.gif" alt="wiggle flaps ghost">

### Ghost with Eyes

Add two `div`s within the ghost-body div and give them a class of `.eyeball`. Then style the eyeballs to have a height, width, border-radius, margin, and display inline-block. Then add `text-align: center` to your `.ghost-body` styles in order to center the eyeballs.

<img class="small" src="{{ site.url }}/web-app/lessons/css-extension-animations/assets/ghost-eyes.gif" alt="ghost with eyes">

### Blinking Ghost

Create another keyframe, `blink`, that changes the height of the eyeballs.

<img class="small" src="{{ site.url }}/web-app/lessons/css-extension-animations/assets/ghost-blinking.gif" alt="ghost with eyes">

### Ghost Shadow

Add a div below the ghost-body div and give it height, width, background-color, and a border-radius. It should automatically float if it's inside of the ghost-container div.

<img class="small" src="{{ site.url }}/web-app/lessons/css-extension-animations/assets/ghost-shadow.gif" alt="ghost with shadow">

[Back to Lesson Index]({{ site.url }}/web-app/lessons)

<!-- ### Finished Product

Take a look at our example below if you're stuck!

<p data-height="378" data-theme-id="0" data-slug-hash="yRRXjx" data-default-tab="css,result" data-user="rwarbelow" data-pen-title="Rachel's Ghost Playground - Finished" class="codepen">See the Pen <a href="https://codepen.io/rwarbelow/pen/yRRXjx/">Rachel's Ghost Playground - Finished</a> by Rachel Warbelow (<a href="https://codepen.io/rwarbelow">@rwarbelow</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script> -->
