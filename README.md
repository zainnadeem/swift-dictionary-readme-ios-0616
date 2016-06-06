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
* The outline/notes below cover a LOT - reference that for what the student should see.

## What the student can do at this point 

* Create variables and constants
* Is familiar with type annotations, type inference and string interpolation.
* Can create functions with return types.
* Is familiar with the String, Int, Double, and Bool type.
* Can perform arithmetic operations on Int and Double.
* Understands if and else clause statements.
* Can create and use Arrays.
* Can iterate over an Array using a for-in loop.
* Can iterate over an Array calling enumerate().
* Work with the following methods on arrays:
	* append()
	* insert(_:atIndex:)
	* removeAtIndex()
	* subscript syntax with arrays
	* count
	* isEmpty
* Had just learned about Optionals!
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
* Think of the `myFavoriteWords` variable as a real-world dictionary. Our keys are represented by the following:
	* "Rigmarole"
	* "Gobbledygook"
	* "Lollygag"
	* "Wabbit"
* With these keys in hand, we can take a key... plug it into our dictionary and get back the definition. So how do we do this?

```swift
let definition = myFavoriteWords["Rigmarole"]
```

* Here... we are taking the "Rigmarole" key and plugging it into our `myFavoriteWords` variable using again a syntax that looks somewhat like we're trying to make an `Array`, but we're NOT.
* If we were to option click the `definition` variable, what do you expect we will see?

![optionalDefinition](http://i.imgur.com/woJfETt.png?1)  
* But I thought the Value was of type `String`, why is it coming back as an optional String? (`String?`)


![confused](https://media.giphy.com/media/3oEjHChKVxgKFLM2ty/giphy.gif)  

* Well... before we dive into that, what if we tried doing something like this.

```swift
let laDiDaDefinition = myFavoriteWords["LA DI DA"]
```
* Is "LA DI DA" a valid key here? What is the type of `laDiDaDefinition` here...?

![la di da](http://i.imgur.com/Ur34J9t.png?1)

* It's also of type `String?` (optional String). Can you see **why** this is the case now?
* If we made an attempt to use a Key that wasn't valid (like above) then the `laDiDaDefinition` variable would be `nil` because there was no value to return.
* The `definition` variable above was created using a valid Key, so the value returned is a `String?` as well... BUT in unwrapping it.. we would be met with a `String` value and NOT `nil`. In unwrapping the `laDiDaDefinition` variable, we would be met with `nil`.

```swift
let definition = myFavoriteWords["Rigmarole"]
if let definition = definition {
    print("The definition of the word Rigmarole: \(definition)")
} else {
    print("Rigmarole is undefined.")
}

// prints "The definition of the word Rigmarole: a lenghty and complicated procedure"


let laDiDaDefinition = myFavoriteWords["LA DI DA"]
if let laDiFrigginDAA = laDiDaDefinition {
    print("The definition of the word LA DI DA: \(laDiFrigginDAA)")
} else {
    print("LA DI DA is undefined.")
}

// prints "LA DI DA is undefined."
```

* Compare that with trying to print those variables WITHOUT unwrapping them:

```swift
let definition = myFavoriteWords["Rigmarole"]

print(definition)
// prints "Optional("a lenghty and complicated procedure")"



let laDiDaDefinition = myFavoriteWords["LA DI DA"]

print(laDiDaDefinition)
// prints "nil"
```

* Using the same style as above, posing the problem at hand then solving it alongside with the student, I want to introduce the following as well.. what if we now wanted to add this la di da to our dictionary and give it a definition (value):

```swift
myFavoriteWords["LA DI DA"] = "pretentious or snobbish, especially in manner or speech"
```

* Of if we hear back from our editor that la di da is a word he/she NO LONGER WANTS!! how can we get rid of it now from our dictionary:

```swift
myFavoriteWords["LA DI DA"] = nil
```

* **NOTE** We should tell them that a dictionary is **NOT** ordered but.. I'm unsure if we should bring that up here. In the next reading, we're set to talk about iterating over a dictionary which is where they will need to know thats the case. **PERSON WRITING THIS**: What do you think?

* You did it!

![congrats](https://media.giphy.com/media/7rj2ZgttvgomY/giphy.gif)






<a href='https://learn.co/lessons/Dictionary' data-visibility='hidden'>View this lesson on Learn.co</a>
