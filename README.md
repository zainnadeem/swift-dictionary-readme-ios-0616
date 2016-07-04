# Dictionary

![Drawing](http://a5.files.biography.com/image/upload/c_fill,cs_srgb,dpr_1.0,g_face,h_300,q_80,w_300/MTE1ODA0OTcxNzcxOTg3NDY5.jpg)

> When you're at the end of your rope, tie a knot and hold on.

## Learning Objectives - The student should be able to...

* Explain that a `Dictionary` is a type, similar to how name is of type `String` in the following code snippet:  

```swift
let name: String = "Theodore Roosevelt"
```
* Explain that a *dictionary* stores associations between keys of the same type and values of the same type in a collection with no defined ordering (from apple doc.).
* Explain why they are using a dictionary. You use a dictionary when you need to look up values based on their identifier similar to how yo use a real-word dictionary to look up the definition for a particular word.

## Dictionaries

Remember the days before Google and Siri when you came across a word you didn't know and had to look it up in a big, heavy dictionary? Think back to those days, if you can still remember them. How is a dictionary organized?

A dictionary lists _words_ and their _definitions_. You have to know a word to find a definition, but once you know a word, finding its definition is a trivial matter. The opposite is not true: You've probably had the experience of wanting to find a word to match a definition, in which case, you'd have to read the entire dictionary until you found the definition you're looking for.

You can think of a dictionary of being a list of word/definition _pairs_. A given word appears _once_ and only once in the dictionary, and is matched with its definition.

Let's call the word a _key_ and its definition a _value_. The entire entry can be thought of as a _key/value pair_.

As it turns out, this structure is used frequently in the real world. Can you think of other things that are organized in key/value pairs? Maybe you remember the days when you had to look up people's phone numbers in the phone book. Phone books were organized much like dictionaries: A person's name was matched with their phone number. If you knew a person's name, you could easily find out their phone number. But if you only had a phone number, you were out of luck, unless you wanted to peruse the entire phone book.

This method of organizing information is so common, in fact, that most programming languages have a similar structure that matches a _key_ with a _value_. These structures are even called _dictionaries_ in computer science parlance because of the obvious similarity to language dictionaries. And guess what? Dictionaries are one of Swift's built-in data structures.

## Swift Dictionaries

Just like real-world dictionaries, Swift's dictionaries are used to associate a _key_ with a _value_. The key can be anything, although it is usually a `String`. Likewise, the value can be anything you want to associate with the key.

To demonstrate, let's recreate a real-world dictionary using a Swift dictionary. We won't do the _entire_ dictionary, since that would take a long time; instead, we'll just demonstrate Swift's dictionaries by making a dictionary that consists of some interesting words.

Here's a cool word: _rigmarole_. Let that one roll off the tongue a few times. Here's the definition of rigmarole: "a lengthy and complicated procedure." Not at all like learning about Swift's dictionaries!

How would you represent this very basic dictionary in Swift code?

Here's how to declare a `Dictionary` variable in Swift and populate it with the definition of rigmarole:

```swift
var favoriteWords = ["rigmarole": "a lengthy and complicated procedure"]
```

Probably looks a bit like an `Array` definition, doesn't it? Can you spot the difference?

Notice that this definition contains a colon (`:`). A `Dictionary` definition in Swift looks a lot like an `Array` definition, except you define both the _key_ and its related _value_, separated by `:`.

The syntax looks similar because a `Dictionary` shares a lot of similarities with `Array`s. They both are lists of items, the difference being that a `Dictionary` associates one item with another. Remember how `Array`s had to contain the same _type_ of data? An `Array` of `String`s could not contain an `Int`, for example—all the items had to be `String`s.

Dictionaries have similar limits. In a `Dictionary`, all of the _keys_ have to be the same type, and all of the _values_ have to be the same type. Keys need not be the same type as values, though. For example, keys could be `Int`s and values could be `String`s, and that would be fine.

You can get a sense of this by examing what Xcode reports as the type of a variable. In your playground, <kbd>Option</kbd>-click on your `favoriteWords` variable. You'll see this popup:

![Dictionary type](https://s3.amazonaws.com/learn-verified/dictionary-type.png)

Notice that the type of `favoriteWords` is `[String: String]`. This syntax indicates that it is a `Dictionary` of `String` keys to `String` values.

You just made your first dictionary in Swift!

![First dictionary!](https://s3.amazonaws.com/learn-verified/andy-excited.gif)

You're not limited to just associated `String`s with other `String`s, though. You can use other types. For example, here's a Swift dictionary that maps an `Int` to its English word (as a `String`):

```swift
var numberWords = [1: "one"]
```

Can you guess the type of `numberWords`? If you guessed `[Int: String]`, you're right!

Let's get back to our dictionary of favorite words. You can easily declare a `Dictionary` containing multiple items by separating them with commas—just like you do with arrays. Here's your `favoriteWords` variable declared with _four_ entries:

```swift
var favoriteWords = [
    "rigmarole": "a lengthy and complicated procedure",
    "gobbledygook": "language that is meaningless; nonsense",
    "lollygag": "spend time aimlessly",
    "wabbit": "weary, exhausted",
]
```

(Note that you don't have to put each item on a separate line. You could have declared this variable in a single line, as long as the items are separated by commas, but putting one item on each line makes it a lot easier to read.)

### Using Dictionaries

So how do you use this dictionary you created? Remember real-world dictionaries: Given a word you know (like "rigmarole"), you can easily look up a definition. Swift dictionaries are no different: Given a _key_ you know, you can easily find a _value_ stored in the dictionary.

Let's say you want to find the definition of "rigmarole". It's pretty easy to look that up. In fact, accessing an item in a dictionary looks the same as accessing an item in an array, except you pass a key in brackets instead of an array index:

```swift
var definition = favoriteWords["rigmarole"]
```

Here, `definition` will be a `String`.

Or wait...no. Take another look. `definition` isn't actually a `String`; it's an _optional_ `String` (that is, it is of type `String?`). You can confirm this by <kbd>Option</kbd>-clicking on it:

![Optional `String`](https://s3.amazonaws.com/learn-verified/dictionary-optional.png)

Why did you get back an optional `String`?

Consider another case: You search for a key that doesn't exist in the dictionary:

```swift
var nonexistentDefinition = favoriteWords["strategery"]
```

"Strategery" isn't even a word, and it's certainly not in the `favoriteWords` dictionary! If you try to get a value for a key that doesn't exist, you will get `nil` back instead.

So: If you access a key in a dictionary, you get `nil` back. That means the return value has to allow for `nil`, which means it _has_ to be an optional type. That's why you get back an optional `String` (`String?`) even if the key _does_ exist in the dictionary.

You can see this if you try to unwrap and print the definitions you retrieved from the dictionary:

```swift
if let definition = definition {
    print("The definition of 'rigmarole' is '\(definition)'")
} else {
    print("'rigmarole' isn't a word!")
}
// prints "The definition of 'rigmarole' is 'a lengthy and complicated procedure'

if let definition = nonexistentDefinition {
    print("The definition of 'strategery' is '\(definition)'")
} else {
    print("'strategery' isn't a word")
}
// prints "'strategery' isn't a word"
```

On second thought, perhaps you decided that you really _do_ like the word "strategery", and want it to be a part of your dictionary of favorite words. How can you add it?

Since `favoriteWords` is a _variable_, you can _add_ new items to it. (If you had declared it as a constant using `let`, however, you would _not_ be able to add items to it, just like you can't add items to a constant array.) It's pretty easy to add "strategery" to your dictionary. Just assign a value to the key:

```swift
favoriteWords["strategery"] = "strategy"
```

You can easily check to see if that key is now a part of your dictionary, either by printing the entire dictionary to the console, or by retrieving the definition using "strategery" as the key:

```swift
definition = favoriteWords["strategery"]
```

Try it out in your playground!

Say later on, a friend points out that "strategery" isn't really a word, so it definitely can't be a favorite word, so you decide to remove it from the dictionary. Removing a key from a dictionary is pretty easy: Just assign that key the `nil` value.

```swift
favoriteWords["strategery"] = nil
```

You can confirm that it has been deleted by printing it to the console. You won't see an entry for "strategery" anymore!

```swift
print(favoriteWords)
// prints ["wabbit": "weary, exhausted", "rigmarole": "a lengthy and complicated procedure", "lollygag": "spend time aimlessly", "gobbledygook": "language that is meaningless; nonsense"]
```

That's enough about dictionaries for now. In future lessons, you'll learn a lot more about them and how powerful they can be.

![Shia LeBeouf clapping](https://s3.amazonaws.com/learn-verified/shia-lebeouf-applause.png)

<a href='https://learn.co/lessons/Dictionary' data-visibility='hidden'>View this lesson on Learn.co</a>
