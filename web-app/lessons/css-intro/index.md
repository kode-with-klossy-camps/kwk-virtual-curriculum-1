---
title: Intro to CSS
---

[Back to Lesson Index]({{ site.url }}/web-app/lessons)

## 🎯 Learning Goals

* Understand the purpose and role of CSS in a webpage
* Understand and use the syntax of a CSS rule
* Experiment with some of the common properties for aesthetic

## 📗 Technical Vocabulary

* CSS
* Declaration
* HTML Element
* Property
* Rule
* Value

## 🗂 Warm Up

Over the next couple of days, we'll create a lot of small websites to practice what we're learning.

Write a list of topics you are interested in or passionate about that you can refer back to when you need to make a small site. Be ready to share your answers!

## 🌎 What is CSS?

CSS stands for **Cascading Style Sheets**. It is a language that allows us to add styles to HTML documents on the web. It’s incredibly powerful!

Take a few minutes to check out the <a target="blank" href="http://www.csszengarden.com">CSS Zen Garden</a>. You'll notice that all of the sites here are created with the exact same HTML document; they were just styled differently with CSS.

You'll learn that there is so much that CSS can do, and there are so many specific ways we can give directions, in code, to style our webpages.

Throughout our first 2 CSS lessons, we'll talk about most of the commonly-used things that CSS can do. By the middle of the week, you'll have most of the CSS tools you'll need to build a beautiful site!

## Syntax

In CSS, we write a set of rules for how our document should look. The browser evaluates those rules and styles the page accordingly. A CSS rule is defined as follows:

<img src="./assets/css-rule.png">

In the example above, the browser will set the color of any text element inside the `<body>` element. We can define multiple sets of properties and values in a given rule.

In the previous section, we said that "there is so much that CSS can do." Each little thing it does comes from a **property**. One example of a property is `color` - and that property can help us change the color of some text. There are many, many properties that we could use. There are some that you will use frequently and quickly memorize. However, you do _not_ need to remember the entire list; there are resources like <a target="blank" href="https://htmldog.com/references/css/properties/">this</a> which you can reference anytime you are coding!

## Text

While we may take it for granted, the decisions that a developer makes for a webpage's text has a huge influence on the experience a user has! Here are some things to notice about any piece of text:

- Font
- Size
- Weight
- Color

Using CSS, we can control all of that! If you visit <a target="blank" href="https://www.tiktok.com/en/">TikTok</a> on a laptop, you'll see a menu on the left-hand side (image below).

<img src="./assets/tiktok.png" alt="Screen shot of TikTok website with simple menu">

Each link that a user can click on has the following CSS rules applied to it. All of these lines of code are there solely to control the look and feel of those small links!

```css
p {
  font-family: 'sofiapro-medium';
  font-size: 16px;
  font-weight: 500;
  color: #000000;
}
```

Let's breakdown the code above, using our vocabulary:
- The entire code snippet is referred to as a **CSS rule**
- The **selector** is `p` - that's the element which will be changed with this rule
- Each line inside the curly braces is a **declaration**
- `font-family`, `font-size`, `font-weight`, and `color` are the four **properties** that are being assigned values in this rule.
- `'sofiapro-medium'`, `16px`, `500`, and `#000000` are the four **values** assigned to their respective properties
- The colons `:` and semi-colons `;` are necessary!

<br>

<div class="try-it">
  <h2>Try It: Style Text</h2>
  <p>We'll be working in repl.it projects again, but today we will use both the HTML <em>and</em> CSS files. Use <a target="blank" href="https://repl.it/@kodewithklossy/try-it-style-text">this repl.it project as a starter.</a> Then, follow these steps:</p>
  <ul>
    <li>Start by writing some HTML so we have some elements to style. Write an <code class="try-it-code">h1</code> element and make sure to include some content between the tags!</li>
    <li>Now, write a CSS rule for the <code class="try-it-code">h1</code>. Inside the rule, write a declaration to change the size and color of your <code class="try-it-code">h1</code>. Find a list of colors to use <a target="blank" href="http://colours.neilorangepeel.com/">here</a>.</li>
    <li>Repeat these steps with an <code class="try-it-code">h2</code>, then a <code class="try-it-code">p</code>, then another <code class="try-it-code">p</code>. Also check out the <code class="try-it-code">background-color</code> property!</li>
  </ul>

  <div class="challenge-container mild-heat">
    <p class="spicy-click">Click here for 2 Mild Challenges 🌶</p>
    <div class="spicy-toggle">        
      <ul>
      <li>Do some google research on how to use hexadecimal codes instead of color names. For example, the hexadecimal code for white is <code class="mild-code">#ffffff</code>. See if you can implement these in your code!</li>
      <li>To add in some really fun fonts, check out <a target="blank" href="https://codepen.io/team/sparkbox/full/OMdwoJ">this how-to guide</a>, then add some fun fonts to your project!</li>
      </ul>
    </div>
  </div>

</div>

## Borders

One of the most helpful CSS properties to use while you are in the process of building a page is `border`. We will get into formatting in the next lesson, but the `border` property really helps you see what space a given element is taking up on the page.

<div class="try-it">
  <h2>Explore: Borders</h2>
  <p>For this activity, you'll be working in the same repl.it project that you started with text and colors.</p>
  <p>Add the declaration: <code class="try-it-code">border: 1px solid red;</code> to each rule in your CSS file. This value looks a little different from most of those we've seen; there are 3 pieces of information.</p>
  <ul>
    <li><strong>1px</strong> refers to the thickness of the line on the border</li>
    <li><strong>solid</strong> refers to the border style, in this case a solid line</li>
    <li><strong>red</strong> is the color that you would like the border to be (it could be changed to any valid color name or hex code!)</li>
  </ul>
  <p>What change did you see on your page when you added this border declaration? Tinker with the 3 pieces of information - change <strong>1px</strong> to <strong>5px</strong>, change the color, etc! Check out all the <a target="blank" href="https://www.w3schools.com/css/css_border.asp">possible border styles</a> as well!</p>
</div>

Takeaways from this exploration:
- Any element can have a border
- We can define how thick the border is, as well as the style  and color
- When we apply the rule, a border is added to all four sides of an element. (If you ever want to apply a border to just one side - google around for `border-bottom`, `border-top`, etc.)
- If we don't define a border, no border will show up!

## Buttons

Before you get information about buttons in CSS, take a minute to explore and reflect on what you already know about them from a _user standpoint_!

<div class="try-it">
  <h2>🐣 Explore: Buttons</h2>
  <p>With your breakout group, visit the <a target="blank" href="https://www.kodewithklossy.com/">Kode With Klossy</a> website in another tab. Find the "Learn More and Apply" button.</p>
  <ul>
    <li>How did you know it was a button?</li>
    <li>What do you observe when you hover your mouse over the button?</li>
  </ul>
  <br>
  <p>Now, visit the <a target="blank" href="https://github.com/">GitHub</a> landing page in another tab. Find the "Sign In" button.</p>
  <ul>
    <li>How did you know it was a button?</li>
    <li>What do you observe when you hover your mouse over the button?</li>
    <li>What is at least one difference between this and the KWK button?</li>
  </ul>
</div>

🌎 Let's translate this into some CSS tools that we can use in the future:

**Kode With Klossy**:
1. The color was the same on the whole button
2. When a user hovers over the button, the color slightly changes
3. When a user hovers over a button, the cursor changes from an arrow to a pointer finger

Here is the code that was used to accomplish this (colors were modified for simplicity):

```css
button {
  background-color: green; /* (#1) */
}

button:hover {
  background-color: light-green; /* (#2) */
  cursor: pointer; /* (#3) */
}
```

The code snippet above includes two things we haven't talked about yet:
- `button:hover`: This is called a `pseudo-selector` - when the button is hovered over, this rule will come into play. If the button is not being hovered over, it will be ignored.
- `cursor: pointer;`: This declaration will change the image that is presented as the cursor. `pointer` provides a little hand that looks like it's pointing with its finger. If you're interested in learning about other cursors you could use, check out <a target="blank" href="https://developer.mozilla.org/en-US/docs/Web/CSS/cursor">this resource</a>.

**GitHub**:
1. The button only has an outline; it's not filled in with the same color
2. The button has rounded corners
3. When a user hovers over a button, the cursor changes from an arrow to a pointer finger

Here is the code that was used to accomplish this:

```css
button {
  border: 1px solid white; /* (#1) */
  border-radius: 3px; /* (#2) */
}

button:hover {
  cursor: pointer; /* (#3) */
}
```

Another declaration that we haven't talked about:
- `border-radius: 3px;`: This is what rounds the corners of the button. `3px` was used for the GitHub Sign In button, but we could provide any value in pixels!

<div class="try-it">
  <h2>Try It: Buttons</h2>
  <p>Create a new repl.it project for this activity.</p>
  <ol>
    <li>In the HTML file, write a button element with the content "Try Pro Free for 7 Days".</li>
    <li>In the CSS file, write the rules necessary to re-create the button pictured below! Use any color you want.</li>
  </ol>
  <img src="./assets/button.png" alt="Bright button with rounded corners">
  <br>

  <div class="challenge-container spicy-heat">
    <p class="spicy-click">Click here for a Spicy Challenge 🌶🌶🌶</p>
    <div class="spicy-toggle">        
        <p>When the button is hovered over, it should look like the image below. Implement the CSS code necessary to re-create that hover state.</p>
        <img src="./assets/button-hover.png" alt="Bright button with rounded corners">
    </div>
  </div>

  <div class="challenge-container spicy-heat">
    <p class="spicy-click">Click here for an Extra Spicy Challenge 🔥🔥🔥</p>
    <div class="spicy-toggle">        
        <p>There is a slight shadow behind the bottom and right side of the button - do some research online to explore how that might be achieved with CSS.</p>
    </div>
  </div>

</div>

## Putting It All Together

In just your first day learning about CSS at Kode With Klossy, you've already learned so much!

Take a minute to write down your key takeaways from this lesson.
- Things that seem the newest to you
- Things that seem most interesting to you
- Questions that are still on your mind

## More Practice/Extensions

For each practice prompt, start a new repl.it project. You'll notice that when you start a new repl.it project, a lot of code is already written in the HTML file. You can delete anything inside of the `<body>` tags, then write your own code! _Hint: One thing that may be helpful for any/all challenges is `text-align: center`!_

<div class="challenge-container mild-heat">
  <p class="spicy-click">Click here for Mild Practice 🌶</p>
  <div class="spicy-toggle">        
    <p>Recreate a button from <a target="blank" href="https://www.kodewithklossy.com/">the Kode With Klossy</a> site.</p>
  </div>
</div>

<div class="challenge-container medium-heat">
  <p class="spicy-click">Click here for Medium Practice 🌶🌶</p>
  <div class="spicy-toggle">        
    <p>You are planning to open your ✨dream✨ business. Make a landing page to let your customers know the name of it, a little bit about it, and a button they can click to let you know they are interested in learning more!</p>
    <p>Make sure you use a border and font-family. For colors, you might want to use <a target="blank" href="https://colorsupplyyy.com/app">Color Supply</a> or a similar site to help pick a palette. To achieve this medium challenge, use hex codes instead of color names (ex: use `#ffffff` instead of `white`).</p>
  </div>
</div>

<div class="challenge-container spicy-heat">
  <p class="spicy-click">Click here for Spicy Practice 🌶🌶🌶</p>
  <div class="spicy-toggle">        
    <p>First, complete the medium challenge. This will build off of that.</p>
    <p>Do some research on classes and IDs. You'll need to utilize one or the other to complete this challenge:</p>
    <ul>
      <li>Create three buttons on your business landing page</li>
      <li>Use CSS selectors rules to style all three buttons <em>differently</em></li>
      <li>Each button should draw on inspiration from a button you've seen on a professional site</li>
    </ul>
  </div>
</div>

[Back to Lesson Index]({{ site.url }}/web-app/lessons)
