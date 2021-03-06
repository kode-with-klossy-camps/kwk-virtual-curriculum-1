---
title: Classes and Objects
---

[Back to all Lessons]({{ site.url }}/swift-ios/lessons)

## 🎯 Learning Goals

* Write a class and create objects from that class
* Explain the difference between a class and an object
* Create dynamic objects using the `init` function and properties

## 📗 Technical Vocabulary

* class
* object
* initializer
* property
* actions

**Note:** For all practice today, scholars will be working in repl.it.

## 🌎 Classes & Objects

When we work with classes, we think about our code in terms of objects. A **class** is like a blueprint or a cookie cutter for our code. It is a chunk of code, usually, in its own file, that can hold data and functions. It kind of serves as a factory - think about a car factory - they have a blueprint, then make thousands of cars from that blueprint. The cars from this blueprint will have a lot in common, but each may have their own differences - colors, fabric for seats, etc.

An **object** is created from a class. Thinking back to that car factory: the class is the blueprint, and the object is the actual car that gets built. Our objects won't be _physical_ objects, but they will be created from our class blueprint, so have some things in common, but can have their own flavor, like an actual car can have a different color.

Together, we are going to make a scholar class. It will be a blueprint for a scholar, and then we will make an individual scholar object using that blueprint.

<div class="try-it">
  <h2>🗂 Brainstorm</h2>
  <p>Make a list of things that all scholars have - they don't have all to be the same. The first thing on the list might be "name". Be ready to share out!</p>
</div>

### Scholar Class

We are about to write a Scholar class, but first, here are a few things you may want to know about classes in general:
* start with keyword `class`, lowercased
* after that, the class name is next, 1st letter capitalized
* open code block with curly brackets - `{}`

```swift
class Scholar {
  // code will go here
}

// calling Scholar() creates an object from the Scholar class:
var newScholar = Scholar()
print(newScholar)
```

The code above isn't much, but it is a class! When this file runs, we will see something like `__lldb_expr_3.Scholar` print out, which looks funky, but what matters most is the ending of `.Scholar`. This tells us that the value of the `Scholar` variable was created from the Scholar class.

Let's add some **properties** to our class:

```swift
class Scholar {
  var grade = 10
  var studying = "Swift"
  var name = "Ophelia"
}

var newScholar = Scholar()
print(newScholar)
```

A **property** is a piece of information that we want to attach to each object made from a class. Right now, every scholar object we create with the Scholar class will be labeled as in grade 10, studying Swift, and named Ophelia.

To illustrate this, we can add some print statements using the dot notation:

```swift
print(newScholar)
//-> __lldb_expr_3.Scholar
print(newScholar.grade)
//-> 10
print(newScholar.studying)
//-> Swift
print(newScholar.name)
//-> Ophelia
```

It's safe to say all scholars in _this camp_ are studying Swift, but it's unlikely that every scholar is in grade 10, and extremely unlikely that everyone has the same name.

Luckily, Swift gives us a way to personalize each object when it's created. It will look similar to the way we pass arguments to functions. We will do this with an **initializer**.

## Initializer

The initializer is a special function inside of a class. `init` is a keyword; if you write a function called `init` inside of a class, it will be called when you create an object from that class. One difference is that we _don't_ use the `func` keyword before `init`.

`init` runs once and only once: when we create a new object from the class. It is written inside the class, below any property variables we declare for that class. It can take arguments, which can help make our class dynamic. In this case, that means giving each scholar their own name.

Let's add this `init` function into our class, giving it an argument of `scholarName`, which is a string.

```swift
class Scholar {

  var grade = 10
  var studying = "Swift"
  var name = ""     // default this to an empty string!

  init(scholarName : String) {
    name = scholarName
  }

}
```

Inside of init, we've re-assigned `name` to whatever `scholarName` was passed in as. This won't work quite yet, because when we call `Scholar()`, we are not passing it a `scholarName` argument like it expects. Let's pass it Scholar(scholarName : "Viola") and re-run.

```swift
var newScholar = Scholar(scholarName : "Viola")

print(newScholar)
//-> __lldb_expr_1.Scholar

print(newScholar.name)
//-> Viola
```

<div class="try-it">
  <h2>Try It: Initializer and Arguments</h2>
  <p>If you didn't code along, get up-to-date on what we have for the scholar class. Then, add another argument and re-assignment in <code class="try-it-code">init</code> for the <code class="try-it-code">gradeLevel</code> so that we can have scholars in different grades!</p>
</div>

## Actions

Classes can have properties AND actions! **Actions** are functions that are associated with a class. Like `init`, they are written inside the `{}` curly braces of the declared class. This means that every object created from a class will have **access** to this function. Let's write one, so we can see it in action.

Here's an example, building on our Scholar class:

```swift
class Scholar {

  var studying = "Swift"
  var name = ""
  var grade = 0

  init(scholarName : String, scholarGrade: Int) {
    name = scholarName
    grade = scholarGrade
  }

  func writeCode() {
    print("\(name) is busy writing code!")
  }

}
```

Now we can check that it's working by calling the method on the object. This looks a lot like the syntax when we call on properties, but we need to **call** the function using the `()`.

```swift
var newScholar = Scholar(scholarName: "Amy", scholarGrade : 11)

newScholar.writeCode()
//-> "Amy is busy writing code!"
```

`writeCode()` is a function, but more specifically an **action** for this class, and this class only. You can even try calling it in the file without the `newScholar` preceding it, and you'll see an error!

<div class="try-it">
  <h2>Try It: Actions</h2>
  <p>Update your code so that you have the <code class="try-it-code">writeCode</code> action. Then, add another method of your choice to the scholar class! Call the action on an object to make sure it's working as expected.</p>
</div>

Just to be clear, actions written inside a class can **only** be called on objects created from that class. If you try to call an action like a normal function, you'll run into problems.

```swift
var newScholar = Scholar(scholarName: "Amy", scholarGrade : 11)

newScholar.writeCode()
//-> "Amy is busy writing code!"

writeCode()
//-> ERROR
```

## Classes vs. Objects

Classes are the blueprints or cookie cutters. Objects are created from the class - in many cases, we will pass an argument in to create a class that changes its properties. There can be MANY objects that are created from just one class!

<div class="practice">
  <h2>Practice: Classes & Objects</h2>
  <h3>Choose Your Own Class</h3>
  <ul>
    <li>With your partner, brainstorm another class. Remember, we used Scholar because all scholars share some things, and also had some unique things about them. If you are struggling for an idea, Car and Dog are both commonly used to practice work with classes 🚗 🐶</li>
    <li>With your partner, write a list of properties your class should have. What is true about every ____? (If you are talking about a car, every car has wheels...)</li>
    <li>What function, or action, do you want your _____ to take? (If it's a dog, I would want it to bark, sit, fetch...) Come up with at least 2 actions!</li>
    <li>Write your class</li>
    <li>Create variables for the properties your class needs</li>
    <li>Write the actions for your class</li>
    <li>Create at least one object with this class and do some printing to make sure your class is behaving as expected</li>
    <li>Add in an <code class="practice-code">init</code> function so you can pass your class something specific to the object you are creating. (For a car, I would definitely want to make sure the color could change!)</li>
  </ul>

  <div class="challenge-container extension-heat">
    <p class="spicy-click">Extension 🕵🏾‍♀️</p>
    <div class="spicy-toggle">        
      <ul>
        <li>Read this
          <a href="https://www.weheartswift.com/swift-classes-part-2/" target="blank">blog post</a>
        </li>
        <li>What is a scenario where you could use a superclass and subclass?</li>
        <li>If you still have time, try to build the superclass and subclass you brainstormed. You can just create a new file in the project you've been working in.</li>
      </ul>
    </div>
  </div>

</div>

<br>
[Back to all Lessons]({{ site.url }}/swift-ios/lessons)
