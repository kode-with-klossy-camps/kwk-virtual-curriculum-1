---
title: Iteration 2: Add & Delete with Core Data
---

## 🎯 Learning Goals

* Students will implement Core Data so that a users to-dos can persist

### Getting Started

* Make sure you've completed [Iteration 1: Dynamic To-Dos]({{ site.url }}/swift-ios/projects/to-do-list/i1) before starting this.

## Core Data

Our ToDo List app is working great now, except nothing is being saved. When we leave our app and come back, none of our ToDos are there. Core Data is going to help us fix that. Core Data allows us to save information from each time we use the app moving forward. Let's get this little database set up!

* In the Navigation Pane of our project, select the file that has the extension `.xcdatamodeld` - this was created when you selected `Use Core Data` when you created your project.
* Click `Add Entity` (an entity is just a special kind of object) at the bottom of the screen - You can either name this Entity within the Document Outline or open the Data Model Inspector and change the name there (I already have a ToDo class and don't want to name my database the same as my class, so I went with `ToDoCD`)
NOTE: This vocab might be a little confusing because we are using a database, but a database is usually dealt with by the back-end of an application. This 'database' is local, on the device. If you have used localStorage with JavaScript, you can compare it to this. It is stored in the browser/app but not sent anywhere, meaning no one but the one user of this one instance of the app could access the data.

<img class="medium" src="{{ site.url }}/swift-ios/projects/to-do-list/assets/todo9.png">

* Add 2 attributes to our ToDoCD entity
  - `name`: type should be *String*
  - `important`: type should be *Boolean*

* For each of these attributes, de-select the `Optional` button in the Data Model Inspector (in the Utilities Pane)
* Also in the Data Model Inspector, set the `Default Value` for the important attribute to `NO`

Let's now head back to our `addTapped` function in our `AddToDoViewController`. Rather than creating a new ToDo object, we need to access Core Data and create a new ToDoCD object. Since we know that the code we have works, let's just comment out all the code inside that function and re-write it.

>As you work through each section below, you very likely will see red errors. Some of those will go away once you follow the next couple of steps, so work through the rest of the directions before you panic.

## Adding To Core Data

* In the `addTapped` function in `AddToDoViewController`, add a new ToDo Core Data object - you have to pass in an entity and a managed object context

```swift
@IBAction func addTapped(_ sender: Any) {

  // we have to grab this view context to be able to work with Core Data
  if let context = (UIApplication.shared.delegate as? AppDelegate)?.persistentContainer.viewContext {

    // we are creating a new ToDoCD object here, naming it toDo
    let toDo = ToDoCD(entity: ToDoCD.entity(), insertInto: context)

    // if the titleTextField has text, we will call that text titleText
    if let titleText = titleTextField.text {
        // we will take the titleText and assign that value to toDo.name
        // this .name and .important came from the attributes you typed in on the Core Data page!
        toDo.name = titleText
        toDo.important = importantSwitch.isOn
    }

    try? context.save()

    navigationController?.popViewController(animated: true)
  }

}
```

Let's do a quick recap! Once we created a new ToDo Core Data object, we set its name and whether or not its important. Then we saved the context and popped the `View Controller` to get back to the ToDo List (Table View).

> Run the application in the simulator and make sure everything is working.

You won't see the new ToDo in the ToDo List yet... we have to ask Core Data for it back. We'll do that in the next section!

>Are you stuck with a red error that says something like `Cannot find ToDoCD in scope`? Select "Product" from the top menu, the select "Clean Build Folder". Then, `cmd + q` out of Xcode. Restart Xcode and the error should be gone. [This is a documented problem and the best work-around that we've found!](https://stackoverflow.com/questions/63603754/swiftui-2-0-coredata-issues-with-new-project-cannot-find-type-item-in-scope)

## Fetching From Core Data

* In the `ToDoTableViewController`, create a new function called `getToDos` - this function is going to fetch our ToDos from Core Data
* Go ahead and call this function inside `viewDidLoad`
* We need to change our `toDos` property on the `ToDoTableViewController` class - we now want to return an array of Core Data ToDos

```swift
var toDos : [ToDoCD] = []
```

* The first thing we need to do in our `getToDos` function is access Core Data (we did this previously in our `AddToDoViewController`)

```swift
func getToDos() {
  if let context = (UIApplication.shared.delegate as? AppDelegate)?.persistentContainer.viewContext {

  }
}
```

* Now we need to fetch the ToDos from Core Data and bring them back as an array of Core Data objects

```swift
func getToDos() {
  if let context = (UIApplication.shared.delegate as? AppDelegate)?.persistentContainer.viewContext {

    if let coreDataToDos = try? context.fetch(ToDoCD.fetchRequest()) as? [ToDoCD] {
        if let theToDos = coreDataToDos {
            toDos = theToDos
            tableView.reloadData()
        }
    }
  }
}
```

**NOTE:** If you are using Swift 5, you may not need to do that last unwrap, your code may look more like:

```swift
func getToDos() {
  if let context = (UIApplication.shared.delegate as? AppDelegate)?.persistentContainer.viewContext {

    if let coreDataToDos = try? context.fetch(ToDoCD.fetchRequest()) as? [ToDoCD] {
            toDos = coreDataToDos
            tableView.reloadData()
    }
  }
}
```

These libraries from Swift are very reliant on the version you are running on, so you may have slightly different code than someone sitting next to you. That's ok. Follow the errors and work through it. You got this!

* Delete `toDos = createToDos()` inside the `viewDidLoad` function - we no longer need to create our fake ToDos since we are fetching them from Core Data (you can delete or comment out our `createToDos` function that we wrote earlier since we are no longer using it)

You may be getting an error in your `tableView` function about a String not being unwrapped. If so, here's how we can fix this problem. Basically, we have to unwrap the name.

```swift
override func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
  let cell = tableView.dequeueReusableCell(withIdentifier: "reuseIdentifier", for: indexPath)

  let toDo = toDos[indexPath.row]

  if let name = toDo.name {
    if toDo.important {
        cell.textLabel?.text = "❗️" + name
    } else {
        cell.textLabel?.text = toDo.name
    }
  }

  return cell
}
```

Right now, `getToDos` is only being called in `viewDidLoad` (when we first come to the page). We need to write some code so that the new ToDos will appear as Core Data is updated.

* Write a new function `viewWillAppear` and call `getToDos` inside this function (we no longer need to call `getToDos` inside `viewDidLoad`, so you can delete it there)

```swift
override func viewWillAppear(_ animated: Bool) {
  getToDos()
}
```

## Deleting From Core Data

Remember earlier when we talked about removing a ToDo and that using Core Data was going to simplify this process for us and not require us to loop over an array to find a specific ToDo... here we go!

* In our `CompleteToDoViewController`, the first thing we need to do is update our `selectedToDo` property - this now needs to either be a type of Core Data ToDo or nil

```swift
var selectedToDo : ToDoCD?
```

> Run the application in the simulator. This causes us a few errors, but no worries... We got this!!

Inside of `viewDidLoad` where we are setting the text of the titleLabel to the selectedToDo.name, we can add a `?` after `selectedToDo` and it will tell our code "if there is a selectedToDo, we'll go ahead and pass it the info it needs; otherwise, we'll set it equal to nil".

```swift
titleLabel.text = selectedToDo?.name
```

We still have a few errors. Let's head back over to our `ToDoTableViewController`... it looks like our `prepare` for segue function is mad at us. When the segue destination is `CompleteToDoViewController`, our if let should now read `if let toDo = sender as? ToDoCD` (instead of just ToDo). _You may need to run `Product ->  Clean Build Folder` to make sure all these changes take effect._

* Let's now add some code to our `completeTapped` function that will delete a selected ToDo from Core Data (Remember: we first need to write that same line of code that will allow us to access Core Data) and pop us back to the ToDo List. This function is in the `CompleteToDoViewController` file.

```swift
@IBAction func completeTapped(_ sender: Any) {     
  if let context = (UIApplication.shared.delegate as? AppDelegate)?.persistentContainer.viewContext {
    if let theToDo = selectedToDo {
      context.delete(theToDo)
      navigationController?.popViewController(animated: true)
    }
  }
}
```

And now we have a fully functional ToDo List application! Great Job!!!

### Commit Your Work

From the top nav, select "Source Control," then "Commit." Follow the steps outlined in the GitHub lesson to commit your work! Your commit message should be something like “Complete Iteration 2.”
