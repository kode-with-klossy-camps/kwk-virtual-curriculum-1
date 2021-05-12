---
title: Conditionals
---

[Back to all Lessons]({{ site.url }}/swift-ios/lessons)

## 🎯 Learning Goals

* User comparison operators to compare variables, strings, and numbers
* Write and understand conditional logic

## 📗 Technical Vocabulary

- Boolean
- Condition
- Conditionals
- Evaluate
- Expression
- Operators
- Statement

**Note:** For all practice today, scholars will be working in repl.it.

## 🌎 Conditionals

Every programming language has conditionals. If you've worked in Python or Java, you've probably seen something similar to what we'll be working on today!

Conditionals let us instruct our program to do something **if** a certain condition is met. In one web application, there can be hundreds if not thousands of conditionals written into the code. Without these conditions, web applications wouldn't be able to customize the experience for each user.

## Comparison Operators

Swift gives us a way to compare values. Each **expression** below will be **evaluated** to a **boolean**, true or false.

```swift
3 < 5
//=> true

4 >= 9
//=> false

7 == 7
//=> true

"karlie" == "karlie"
//-> true

"karlie" == "Karlie"
//-> false
```

Notice the `==`. This checks if two pieces of data are equal to each other. The assignment operator (`=`), assigns the value of a variable. These two are **very** different!

<div class="try-it">
  <h2>Explore: Operators</h2>
  <p>Look at each expression below and the value it evaluates to. Based on that information, try to determine what that operator does.</p>
</div>

```swift
3 != 4
//=> true

5 != 5
//=> false

4 != 9
//=> true
```

The `not equal` operator - `!=` - checks that two values are not equal. It is the opposite of our `==` operator - the first `=` is replaced with an `!`.

```swift
11 % 2
//=> 1

32 % 6
//=> 2

16 % 3
//=> 1

15 % 3
//=> 0
```

The `modulo` operator - `%` - finds the remainder of two numbers. It is a helpful tool to determine if numbers are even or odd. Learn more <a target="blank" href="https://www.codevscolor.com/swift-odd-even-check/">here</a>!

### Comparing Variables

We can use our comparison operators on variables as well! Let's look at this example:

```js
var language = "Swift"

language == "swift"
//=> false

language == "Swift"
//=> true

"swift" == language
//=> false

var year = 2021
var nextYear = 2022

year > 2000
//=> true

year != 2019
//=> true

year < nextYear
//=> true
```

<div class="try-it">
  <h2>Try It: Comparison Operators</h2>
  <p>Declare two variables - <code class="try-it-code">firstName</code> and <code class="try-it-code">age</code>, and assign them to appropriate values. Now, check for the following things:</p>
  <ul>
    <li>Is your firstName the same as "Karlie"?</li>
    <li>Is your age the same as 15?</li>
    <li>Is your age not the same as 15?</li>
    <li>Is your age greater than 7?</li>
    <li>Is your age less than or equal to 10?</li>
    <li>What is the remainder when your age is divided by 2?</li>
  </ul>

  <div class="challenge-container medium-heat">
    <p class="spicy-click">Click here for a Medium Challenge 🌶🌶</p>
    <div class="spicy-toggle">        
      <p>Have you ever tried to create a password, but the application told you you need at least 8 characters? Time to solve a real-world challenge! Declare a new variable called <code class="medium-code">fakePassword</code> and assign it to a string of your choice. Then, check that the value stored in <code class="medium-code">fakePassword</code> is greater than or equal to than 8 characters. Change the string that <code class="medium-code">fakePassword</code> is assigned to a  couple times to make 100% sure it's working as expected.</p>
    </div>
  </div>

</div>

### Logical Operators

Logical operators allow us to do some even more powerful work:

```swift
var language1 = "JavaScript"
var language2 = "Swift"

print((language1 == "JavaScript") || (language2 == "JavaScript"))
// true

print((language1 == "Swift") || (language2 == "Swift"))
// // // true

print((language1 == "Python") || (language2 == "Python"))
// // // false

print((language1 == "JavaScript") && (language2 == "JavaScript"))
// // // false

print((language1 == "Swift") && (language2 == "Swift"))
// false
```

<div class="try-it">
  <h2>Try It: Logical Operators</h2>
  <p>For this Try It, write all your code in the repl from the previous activity. You will need to use <code class="try-it-code">print()</code> to check the output of your statements.</p>
  <p>Use the same two variables as the previous activity - <code class="try-it-code">firstName</code> and <code class="try-it-code">age</code>, and assign them to appropriate values. Now, check for the following things:</p>
  <ul>
    <li>Is your age less than 30 and greater than 10?</li>
    <li>Is your age less than 20 or greater than 10?</li>
    <li>Is your age exactly 15 or less than 18?</li>
    <li>Is your age greater than 12 or exactly 14?</li>
    <li>Is your age greater than 10 but not exactly 16?</li>
  </ul>
</div>

## Conditionals

Just like in real life, programming is full of decisions. We usually make decisions based on our current state or mood.

**A real-life example:**

Am I hungry?

  Yes ➡ I'll eat

  No  ➡ I won't eat

**A programming example:**

Do you have an account?

  Yes ➡ Please log in

  No  ➡ Please create an account

<br>

Swift gives us a way to ask those questions **and** provide different outcomes based on the answer. They are called **conditionals**. Here's an example:

```js
var queen = "Beyoncé"

if queen == "Beyoncé" {
  print("You are correct!")
} else {
  print("Beyoncé is the only queen.")
}
```

For the example above, "You are correct!" will print to the console. Let's break this down line-by-line.

```js
var queen = "Beyoncé"            // new variable created

if queen == "Beyoncé" {          // program checks for this condition
  print("You are correct!")      // if it evaluates to true, it will execute this block
} else {                         // if it evaluates to false, it will execute this block
  print("Beyoncé is the only queen.")
}
```
We call this entire piece of code an `if statement`.

After the keyword `if`, we have to give Swift an expression that can evaluate to `true` or `false`. That expression is called a **condition**.
- If the condition evaluates to `true`, the code in the block below it will execute or run. It will then ignore the rest of the options.
- If it evaluates to `false`, it will check the condition in the next block.

<div class="try-it">
  <h2>Try It: Conditionals</h2>
  <ul>
    <li>Create a variable named <code class="try-it-code">luckyNumber</code> and assign it to a number of your choice.</li>
    <li>Write an if statement checking if <code class="try-it-code">luckyNumber</code> is less than 50, which if evaluated to true, prints out a sentence (you choose!). If it is evaluated to false, it should print out a different sentence.</li>
  </ul>

  <div class="challenge-container medium-heat">
    <p class="spicy-click">Click here for a Medium Challenge 🌶🌶</p>
    <div class="spicy-toggle">        
      <p>Using your <code class="medium-code">luckyNumber</code>, write a new conditional. If the lucky number equals 13, the output should be "You got it!". If it is too high, the output should be "Guess lower...", and it is too low, the output should be "Guess higher..."</p>
    </div>
  </div>

  <div class="challenge-container spicy-heat">
    <p class="spicy-click">Click here for a Spicy Challenge 🌶🌶</p>
    <div class="spicy-toggle">        
      <p>Using your <code class="spicy-code">luckyNumber</code>, write a new conditional. If the lucky number equals 13, the output should be "You got it!". If it is not, the output should be customized based on how far the number is from the <code class="spicy-code">luckyNumber</code>. There should be one output when the number is within 10 of the lucky number, and one when there's a difference of more than 10. For example, if the number is 20, the output might be: "So close, you are just 7 off.". If the number is 100, the output might be "Ouch you are not even close. Off by 87!".</p>
    </div>
  </div>

</div>

Sometimes we may want to provide more than two options. Look at the use of `else if`:

```js
var queen = "Beyoncé"

if queen == "Beyoncé" {
  print("You are correct!")
} else if queen == "Elizabeth II" {
  print("I guess you are technically right...")
} else {
  print("Beyoncé is the only queen.")
}
```

Takeaways:
- We can use any comparison operator in a condition
- We can use strings or numbers in a condition
- If a condition evaluates to true, the code below (block) it will run
- Only one block of code will run for each `if` statement

<div class="try-it">
  <h2>Try It: Conditionals</h2>
  <ul>
    <li>Create a variable named <code class="try-it-code">favoriteFood</code> and assign it to a string of your favorite food</li>
    <li>Write an if statement comparing your favorite to "Chipotle", which if evaluated to true, prints out a sentence of your choice</li>
    <li>Write an else if statement comparing your favorite to "Starbucks", which if evaluated to true, prints out a sentence of your choice</li>
    <li>Write another else if - you choose what you compare it to</li>
    <li>Write an else statement that prints out a sentence of your choice</li>
    <li>Try changing the value of your <code class="try-it-code">favoriteFood</code> variable to "Chipotle", then "Starbucks" (if it wasn't already). Do you get what you expected?</li>
  </ul>
  <br>

  <div class="challenge-container medium-heat">
    <p class="spicy-click">Click here for a Medium Challenge 🌶🌶</p>
    <div class="spicy-toggle">
      <p>Write a program that checks a string. It should print to the console "even" if the number of characters in the text is even, and "odd" if the number of characters in the text is odd.</p>
    </div>
  </div>

</div>

## Conditionals

<div class="practice">
  <h2>Practice: Operators & Conditionals</h2>
  <p>For each of these exercises, you should use <code class="practice-code">print</code> to print your output or feedback.</p>
  <p>Declare a variable called <code class="practice-code">numberOfScholars</code> and assign it to any number. Write a condition that checks the number of scholars. If there are less than 24, output "There is room for more - welcome!". If there are already 24 or 25 scholars, output "Oh no, we're going to have to put you on the waiting list." If there are more than 25 scholars, output "We are so sorry but we are booked. Would you like to sign up for next year?"</p>

  <div class="challenge-container medium-heat">
    <p class="spicy-click">Click here for a Medium Challenge 🌶🌶</p>
    <div class="spicy-toggle">        
      <p>Declare a new variable <code class="medium-code">number</code> and assign it to any number. If it is a multiple of 3, print "Fizz". If it is a multiple of 5, print "Buzz". If it is a multiple of both 3 and 5, print "FizzBuzz". If it isn't a multiple of 3 or 5, just print out the number.</p>
    </div>
  </div>

  <div class="challenge-container spicy-heat">
    <p class="spicy-click">Click here for a Spicy Challenge 🌶🌶</p>
    <div class="spicy-toggle">        
      <p>Have you ever tried to create a password, but the application told you that <em>you need at least 1 number and between 8 and 14 characters total</em>? Time to solve another real-world challenge! Declare a new variable called <code class="spicy-code">fakePassword</code> and assign it to a string of your choice. Write a conditional that checks the value of <code class="spicy-code">fakePassword</code> and gives appropriate feedback on if it is a valid password (contains at least 1 number and between 8 and 14 characters total).</p>
    </div>
  </div>

</div>

<br>
[Back to all Lessons]({{ site.url }}/swift-ios/lessons)
