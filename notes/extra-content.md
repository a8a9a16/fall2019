---
title: DPS923 MAP523 Week 5
layout: default
---

## DPS923 MAP523 Week 5 Notes

The theme for this week is to improve the appearance of the example app. Along the way, a number of app configuration and programming techniques are learned. 

We also get more coverage of the Swift programming language. 

<br>

### Monday plan

Test 1 is today. 

Then, the professor will guide you through the topic hightlights in the textbook. 

Chapter 9: The New Look  
Chapter 10: The Final App  
Chapter 11: The Final App  
Chapter 12: The Final App  

TBA - Swift basics  

```swift

// Create a new "Swift File" named something like
// "ModelClasses.swift" to hold ALL entity model classes

class Person {
    var name: String = ""
    var age: Int = 0
}

// How to use this... assume you're in a Playground 
// or in the viewDidLoad() method

let peter = Person()
peter.name = "Peter"
peter.age = 23

let myriam = Person()
myriam.name = "Myriam"
myriam.age = 25

var people: [Person] = [peter, myriam]

let pavan = Person()
pavan.name = "Pavan"
pavan.age = 23
        
let tiago = Person()
tiago.name = "Tiago"
tiago.age = 25
        
people.append(pavan)
people.append(tiago)

// How many items in the array?
var num = people.count




```

<br>

### Wednesday plan

Hands-on: Your professor will guide you in an interactive activity that introduces you to two important topic areas:  
1. Swift and arrays  
2. Table view in iOS  

The Swift documentation for [info on arrays](https://docs.swift.org/swift-book/LanguageGuide/CollectionTypes.html) (in the Collection Types topic).

See the iOS Human Interface Guidelines documentation for [info on tables](https://developer.apple.com/design/human-interface-guidelines/ios/views/tables/). 

It includes a link to the [Table View Programming Guide for iOS](https://developer.apple.com/library/archive/documentation/UserExperience/Conceptual/TableView_iPhone/AboutTableViewsiPhone/AboutTableViewsiPhone.html) - all good stuff. 

If there's time remaining, work on Assignment 2.

<br>

#### This week's Swift focus

Arrays

<br>

### Learning resources

iOS Apprentice  
Chapters 7, 8

Swift documentation  
[Tour](https://docs.swift.org/swift-book/GuidedTour/GuidedTour.html)  
[Guide](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html)

<br>

Declare it as an [implicitly unwrapped optional](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID334). 


= = = = = =  

Cut from A2 at the last moment

<span style="color: blue">DPS923 students:<br>
The app also allows the user to update performance data, by entering new statistical values.</span>

MAP523 students - you're done. 

DPS923 students - continue with the next task.

<br>

<span style="color: blue">DPS923 students:<br>
The app also allows the user to update performance data, by entering new statistical values.</span>

### Update performance data

<br>
<br>
<br>
**more to come**
<br>
<br>
<br>

<br>



<br>

Cut from 2019 Fall week 1/2 notes:

#### Dismiss the keyboard

Today, you will learn that a text field's `resignFirstResponder()` function will dismiss the keyboard. You saw us use that in a button-handling function. We have another way to dismiss the keyboard.  

We will now introduce you - gently - to delegation. We will add a function that will handle the on-screen keyboard's "return key" button tap. In effect, the text field is *delegating* the responsibility of handling that event, to some new code that we will write.  

There are two steps to complete:  
1. Set the text field 'delegate' property to the view controller  
2. Write code to handle an event  

On the storyboard, select the text field. Then, make a connection (press and hold Control, then click-drag-drop) to the "View Controller" icon in the dock at the top of the scene. A connection popup will appear. In the Outlets area, select "delegate".

In the view controller code, edit the class declaration to look like this, by adding a "protocol declaration":  

```swift
class ViewController: UIViewController, UITextFieldDelegate {
```
<br>

Then, add the following function to the view controller:

```swift
func textFieldShouldReturn(_ textField: UITextField) -> Bool {

    // add code to do things, if desired

    return textField.resignFirstResponder()
}
```
<br>

