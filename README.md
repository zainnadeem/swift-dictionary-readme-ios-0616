# Dictionary

<img src="http://a5.files.biography.com/image/upload/c_fill,cs_srgb,dpr_1.0,g_face,h_300,q_80,w_300/MTE1ODA0OTcxNzcxOTg3NDY5.jpg" alt="Drawing" style="width: 200px;"/>  


> When you're at the end of your rope, tie a knot and hold on. 

## Learning Objectives - The student should be able to..

* Explain that a `Dictionary` is a type, similar to how name is of type `String` in the following code snippet:  

```swift
let name: String = "Theodore Roosevelt"
```
* Explain that a *dictionary* stores associations between keys of the same type and values of the same type in a collection with no defined ordering (from apple doc.).
* Explain why they are using a dictionary. You use a dictionary when you need to look up values based on their identifier similar to how yo use a real-word dictionary to look up the definition for a particular word.

## What the student can do at this point 

* More stuff

## Outline / Notes

*  In defining what the dictionary is to the student, it's important to give them the WHY? and include cone snippets or even pseudocode as to what problem they are solving by using dictionaries. 
* Unless you think there's a better way to convey the why a student will use a dictionary, what I had in mind.. was first having them think of the problem they were solving by thinking about a real-world dictionary.
* If you wanted to look up the word **Rigmarole** in a dictionary, you go diretly to the page that contains **Rigmarole** where you're met with the following definition: *a lenghty and complicated procedure*.
* How then can we represent this in code? The idea that there's this word and if we go and find this word, we're met with a definition. In working with dictionaries in swift, the word Rigmarole would be considered the **Key** and the definition would be considered the **Value**. In this simle example, we have one **Key, Value** pairing, but a dictionary contains MANY MANY **Key, Value** pairings (which is what makes up the dictionary).
* The various **Key**'s in a dictionary need to be of the same type. In this example, our key is of type `String`. 
* The various **Value**'s in a dictionary need to be of the same type as well. In this example, our value is of type `String`.
* So if we know our Key's will be of type `String` and the values to those keys will be of type `String` then we can go ahead and create our dictionary!

```swift
var myFavoriteWords = ["Rigmarole": "a lenghty and complicated procedure"]
```
* We just made our first dictionary in swift!

![celebrate](https://media.giphy.com/media/LSNqpYqGRqwrS/giphy.gif)

* Now, this sort of looks like an `Array`, we have the `[` `]` that we're used to seeing with arrays... but there's one difference, can you spot it? `:` is the difference. This separates our Key/Value pairing. To the left of the `:` is our Key - "Rigmarole" and to the right of the `:` is our Value - "a lenghty and complicated procedure".
* If we were to option click the `myFavoriteWords` variable above, we would be met with the following declaration:

![dictionaryDeclaration](http://i.imgur.com/2ecO3Rq.png?1)
* Well.. this should make sense to us now considering what we know. We know that a dictionaries Keys must be of the same type, and the values must be of the same type. Here, our keys must be of type `String` and our values must be of type `String`. With type inference, the compiler is able to figure this out based upon the fact that "Rigmarole" and "a lenghty and complicated procedure" are string literals. 
* This doesn't mean though that values type has to be the same as the keys. What do we mean by that?

```swift
var numbers = ["One": 1]
```

* If we were to option click numbers here, what do you think the type declaration will be?
![stringInt](http://i.imgur.com/D4M6NfO.png?1)

* So.. here we have a dictionary of type `[String: Int]` where the keys must be of type `String` and the values must be of type `Int`. 

* But what if we want our dictionary to REALLY represent some sort of real-world dictionary, how can get have this thing contain more key value pairs like so:

```swift
var myFavoriteWords = [
    "Rigmarole": "a lenghty and complicated procedure",
    "Gobbledygook": "language that is meaningless; nonsense",
    "Lollygag": "spend time aimlessly",
    "Wabbit": "weary, exhausted"
]
```

* We could have just as easily defined it like so (there is on difference at the end of the day). The example above (with how we spaced it) is easier to read in my opinion:

```swift
var myFavoriteWords = ["Rigmarole": "a lenghty and complicated procedure", "Gobbledygook": "language that is meaningless; nonsense", "Lollygag": "spend time aimlessly", "Wabbit": "weary, exhausted"]

// no difference from the one above.
```

* What did we do? Well you'l notice that we have multiple Key Value pairs in our dictionary. We are also following the rules, our keys are of the same type (all `String`'s, and our values are of the same type, all `String`'s). 
* We also separated these varoius pairings using commas to allow for us to store multiple key, value pairs in our dictionary.
* Ok, so far so good! We can make a dictionary with multiple key, value pairs:

![dance](https://media.giphy.com/media/xT1XGHkP7hqm0JvWrS/giphy.gif)

* But, how do we use this thing we just made?
* Think of the `myFavoriteWords` variable as a real-world dictionary. Our keys are represented by the following 



<a href='https://learn.co/lessons/Dictionary' data-visibility='hidden'>View this lesson on Learn.co</a>
