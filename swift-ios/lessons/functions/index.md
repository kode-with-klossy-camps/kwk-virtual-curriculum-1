---
title: Functions
---

[Back to all Lessons]({{ site.url }}/swift-ios/lessons)

## 🎯 Learning Goals

* Be familiar with the syntax to write and call a function
* Explain the flow of arguments/variables through a function

## 📗 Technical Vocabulary

- Argument
- Call/Run
- Declare
- Function
- Parameter
- Return Value

**Note:** For all practice today, scholars will be working in repl.it.

## 🐣Warm Up

In your breakout groups, choose one application that you all like to use.

You will have one minute to click/tap through the application as you normally would while using it.
- Partner A should be the "user" - tapping, scrolling, etc.
- Partner B should be tallying the number of times the application DOES something (examples: load content, respond to a click/tap by showing a different screen or new content, etc.)

To build a mobile application, developers write A LOT of functions. Every time you click a button and see something happen, a function (or many functions) just performed its job. Every time you see new data load (your account page, someone else's profile page, detail of an image, etc.), a function just performed its job.

As we start learning about functions today, we won't be writing ones quite as involved as some that are powering your favorite apps - but we will begin to understand the foundations!

## 🌎 What is a Function?

A function is an action in our code. It has a specific job, and it sits around waiting to be asked to perform it. It can do this job as many or as few times as we tell it to. A function can have a very small job (add two numbers together) or a very big job (find the standard deviation of 1 million numbers). We get to write them, so we have control over what each function does!

In our class example today, we will write instructions for a robot to walk a dog.

## Declare a Function

Here's what a very basic function **declaration** looks like:

```swift
func walkDog() {
  // code goes here
}
```

We start with the key word `func`, then name our function whatever we want. The name should describe the type of action our function is taking. Like variables, we use `camelCase` for multi-word functions.

Directly after the function name, we see open and close parentheses - `()`, then open and close curly brackets - `{}`. The directions we want our function to take will live _inside_ the curly braces. We can give a function as many directions as we'd like!

Let's add some of the steps our robot needs to take to walk a dog. For now, we will use `print()` to print out the steps, so we know when our function is working.

```swift
func walkDog() {
  print("Put on leash")
  print("Put treats in pocket")
  print("Put poop bag in pocket")
}
```

Now, this code alone won't do anything. We have **declared** the function - told it what its job is. But we haven't **called** the function - or told it to carry out its job.

## Call a Function

We have a really nice function written, but we need to **call** it for it to run. The great thing about functions is you, as the developer, can decide when they do their job. Maybe we only want one certain function to run when a user interacts with our site in a specific way. This puts us in complete control.

```swift
func walkDog() {
  print("Put on leash")
  print("Put treats in pocket")
  print("Put poop bag in pocket")
}

walkDog()
```

The last line of the code snippet is what **calls** the function. If we run this code in a repl.it file, we should see each step printed out.

<div class="try-it">
  <h2>Try It: Declaring & Calling a Function</h2>
  <p>Declare and call a function named <code class="try-it-code">sayHello</code>. Write 2-4 <code class="try-it-code">print</code> statements in it, saying whatever you'd like. Verify that it is running successfully by checking the console for the sentences.</p>
  <p>Declare and call a function named <code class="try-it-code">sayGoodbye</code>. Write 2-4 <code class="try-it-code">print</code> statements in it, saying whatever you'd like. Verify that it is running successfully by checking the console for the sentences.</p>

  <div class="challenge-container medium-heat">
    <p class="spicy-click">Click here for a Medium Challenge 🌶🌶</p>
    <div class="spicy-toggle">        
      <p>Did your <code class="medium-code">sayHello</code> sentences print before or after your <code class="medium-code">sayGoodbye</code> sentences? Why? Try changing something in your code so that the order is reversed!</p>
    </div>
  </div>

</div>

## Arguments and Parameters

If we are really going to have this robot help out, we need it to be a little 'smarter'. We need it to know that if there are two dogs, it needs to put two leashes on, bring two poops bags, etc.

We can make functions a little 'smarter' with something called an **argument** and a **parameter**. Check out the code below, and then we'll talk about what is happening:


```swift
func walkDog(numberOfDogs : Int) {
  print("There are \(numberOfDogs) dogs in the house")
}

walkDog(numberOfDogs : 2)
//=> There are 2 dogs in the house 

walkDog(numberOfDogs : 7)
//=> There are 7 dogs in the house 
```

To allow our functions to be more _dynamic_ or work in more situations, we can write the declaration with **parameters**. The parameter(s) live inside the parenthesis right after the function name. If there are more than one, they should be separated by a comma and a space.

When we call the function, it will now be expecting an **argument**. The argument is the value(s) you want to store to the parameter variable(s).

In our example above, `walkDog(numberOfDogs: 2)` was called. `2` was the argument that was passed in. So, the parameter `numberOfDogs` is now a variable that holds the value of `2`. Anytime `numberOfDogs` is referenced inside of this function for this one specific time it's being run it will point to the value of `2`.

Below, `walkDog(numberOfDogs: 7)` was called. Anytime `numberOfDogs` is referenced inside of this function for this one time its being run it will point to the value of `7`.

### Using Parameters Like Variables

We can also do some calculations with our parameters, just like we've done with variables. Let's say we want to set an expectation that the robot walks each dog for 15 minutes. We can use the parameter to tailor the total number of minutes walked for each walk.

```swift
func timeToWalk(numberOfDogs : Int) {
  var totalMinutes = numberOfDogs * 15
  print("You should walk a total of \(totalMinutes) minutes.")
}
```

<div class="try-it">
  <h2>Try It: Arguments & Parameters</h2>

  <div class="challenge-container mild-heat">
    <p class="spicy-click">Click here for a Mild Challenge 🌶🌶</p>
    <div class="spicy-toggle">        
      <p>Write a function that will take 1 argument when called, a number. The function should <code class="mild-code">print</code> the sum of that number and 5. Make sure to name your function something related to its job.</p>
    </div>
  </div>

  <div class="challenge-container medium-heat">
    <p class="spicy-click">Click here for a Medium Challenge 🌶🌶</p>
    <div class="spicy-toggle">        
      <p>Write a function that will take 2 arguments when called, both being numbers, and that will <code class="medium-code">print</code> the sum of those two numbers. Make sure to name your function something related to its job.</p>
    </div>
  </div>

  <div class="challenge-container spicy-heat">
    <p class="spicy-click">Click here for a Spicy Challenge 🌶🌶</p>
    <div class="spicy-toggle">        
      <p>Write a function that will take 3 arguments when called, all being numbers. It should sum the first two numbers, then multiply that sum by the third number and <code class="spicy-code">print</code> the result. Make sure to name your function something related to its job.</p>
    </div>
  </div>
</div>

## Return Values

Up until now, inside our functions, we've only called `print` on values - in the future, we will need our functions to return values so we can use them elsewhere. This may not completely make sense now, but in the next couple of lessons, all the pieces will tie together. It's good to get some exposure to it today.

```swift
func timeToWalk(numberOfDogs : Int) -> Int {
  var totalMinutes = numberOfDogs * 15
  return totalMinutes
}
```

In this function, we are not calling `print`, so when we call it, we won't see an output in the console.

```swift
func timeToWalk(numberOfDogs : Int) -> Int {
  var totalMinutes = numberOfDogs * 15
  return totalMinutes
}

var minutes = timeToWalk(numberOfDogs : 3)
print("You should walk a total of \(minutes) minutes.")
//=> You should walk a total of 3 minutes.
```

Important things to know about returning a value:
- We must indicate that we want to return a value in two different places in the function declaration:
  1. After the parenthesis where we declare any parameters, we must include `-> [DATA TYPE TO BE RETURNED]`
  2. The last line of the function must use the `return` keyword, and the data we want to return should follow it
- Each function can only return **one** value
- Once the program reads the `return` keyword and the rest of the code on that line, it will exit that function. So, any code written on a line after the `return` statement will never be executed.

<div class="try-it">
  <h2>🐣 Explore & Discuss</h2>
  <p>In your breakout group, read through each line of the code above. With as much technical vocabulary as possible, explain what is happening at each line.</p>
</div>

Takeaways:
- `func timeToWalk(numberOfDogs : Int) -> Int {` declares the function
- `(numberOfDogs : Int)` states that we plan to get one piece of data when this function is called. It must be an Integer returned when we call `numberOfDogs`
- `-> Int` declares that we plan to return an Integer out of this function
- `var totalMinutes = numberOfDogs * 15;` declares a new variable that stores the result of 15 multiplied by the number passed into the function
- `return totalMinutes;` returns the value of the `totalMinutes` variable (which is an Integer)
- `var minutes = timeToWalk(numberOfDogs : 3);` calls the function `timeToWalk` and passes in 3 as the argument. The return value of that is stored in the new variable `minutes`

### Incorporating Conditionals

If we were only walking 1 dog, the sentences would read incorrectly, for example, "put on 1 leashes". Let's write a conditional inside the function; if the `numberOfDogs` passed in is 1, we will print out one set of directions, and if it is greater than 1, we will print out another set.

```swift
func walkDog(numberOfDogs : Int) {
  if numberOfDogs == 1 {
    print("Put on \(numberOfDogs) leash")
    print("Put \(numberOfDogs) treat in pocket")
    print("Put \(numberOfDogs) poop bag in pocket")
  } else {    
    print("Put on \(numberOfDogs) leashes")
    print("Put \(numberOfDogs) treats in pocket")
    print("Put \(numberOfDogs) poop bags in pocket")
  }
}
```

<div class="try-it">
  <h2>Try It: Logic Inside a Function</h2>
  <p>Write a function that takes one argument, a <code class="try-it-code">gradeLevel</code>. It should then print out "You are in elementary school" or "You are in middle school", etc. based on the grade level passed in.</p>
  <p>Now, write another function that takes in a number, a <code class="try-it-code">dogAge</code>, and multiplies it by 7. It should print out a sentence telling the dog how old it is in human years.</p>
</div>

## Functions

Throughout camp, we will write a lot of functions! They will have different jobs, and some will look quite different from ours today, but you've got a great foundation. Get a little more practice by completing one or more tasks below.

<div class="practice">
  <h2>🐣 Practice: Function</h2>

  <div class="challenge-container mild-heat">
    <p class="spicy-click">Click here for a Mild Challenge 🌶</p>
    <div class="spicy-toggle">        
      <ul>
        <li>With your breakout group, brainstorm another task you'd like to have this robot complete. You should agree on using the same task. That way, you can check in with each other throughout the lab. Once you've decided on a task, share with an instructor to make sure it will work for all activities, then go to the next step</li>
        <li>In your notebook, write out the small steps that your robot needs to take to complete the task</li>
        <li>In your repl.it file, declare and call the function. The code block should be empty, so nothing should really happen. This is a good step to take to make sure there are no errors</li>
        <li>To make 100% sure you are calling it correctly, write a print statement into the code block and make sure that appears in your console</li>
        <li>Now, write a print statement for each of the commands you wrote down in your notebook. Are they all printing out as expected?</li>
      </ul>
    </div>
  </div>

  <div class="challenge-container medium-heat">
    <p class="spicy-click">Click here for a Medium Challenge 🌶🌶</p>
    <div class="spicy-toggle">        
      <ul>
        <li>Building off of what you've already written in your function - what information could you give it to show different situations?</li>
        <li>Comment out your first function, and start over. This time, your function declaration should ask for an argument. It doesn't necessarily have to be an integer like the class example!</li>
        <li>Finish writing your function</li>
        <li>Call your function a few times, passing in different arguments each time</li>
      </ul>
    </div>
  </div>

  <div class="challenge-container spicy-heat">
    <p class="spicy-click">Click here for a Spicy Challenge 🌶🌶🌶</p>
    <div class="spicy-toggle">        
      <ul>
        <li>With your breakout group, decide what information you want to return out of your function. What data type is most appropriate (string, integer, etc.)?</li>
        <li>In the declaration, tell your function you plan to return a value</li>
        <li>Use the return keyword to return the desired value</li>
        <li>Check yourself: did you return a number like "4" or a string like "Good job!"? To make this function dynamic, we should probably be returning a <em>variable</em> that's storing something calculated based on the argument passed in. Look back at the class example if you are stuck on this part!</li>
        <li>Call your function a few times, passing in different arguments each time. STOP!</li>
        <li>Before you run your code, talk with your partner. What is the expected output/return value?</li>
      </ul>
    </div>
  </div>

  <div class="challenge-container extension-heat">
    <p class="spicy-click">Extension: Multiple Arguments & Return Values 🕵🏾‍♀️</p>
    <div class="spicy-toggle">        
      <ul>
        <li>What is another argument that could be passed in your function? Try it out! Not sure what the syntax looks like? You got this. Remember, strong developers are strong Googlers, so feel free to look for examples online.</li>
        <li>Can you have more than 1 return value? How do you know?</li>
      </ul>
    </div>
  </div>

</div>

<br>
[Back to all Lessons]({{ site.url }}/swift-ios/lessons)
