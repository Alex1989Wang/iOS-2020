# Session 3

Key points covered in session 3. 

## Strings and Characters

A string is a series of characters, such as "hello, world". 

### Create String from String Literal

A string literal is a sequence of characters surrounded by double quotation marks (").

```swift
let someString = "Some string literal value"
```

### Create a Character from Character Literal

```swift
let exclamationMark: Character = "!"
```

### Empty String

```swift
var emptyString = ""               // empty string literal
var anotherEmptyString = String()  // initializer syntax
// these two strings are both empty, and are equivalent to each other

if emptyString.isEmpty {
    print("Nothing to see here")
}
// Prints "Nothing to see here"
```

### String Mutability

```Swift
var variableString = "Horse"
variableString += " and carriage"
// variableString is now "Horse and carriage"

let constantString = "Highlander"
constantString += " and another Highlander"
// this reports a compile-time error - a constant string cannot be modified
```

### Working with Characters

You can access the individual Character values for a String by iterating over the string with a for-in loop:

```swift
for character in "Dog!🐶" {
    print(character)
}
// D
// o
// g
// !
// 🐶
```

### Concatenating Strings and Characters

```swift
String values can be added together (or concatenated) with the addition operator (+) to create a new String value:

let string1 = "hello"
let string2 = " there"
var welcome = string1 + string2
// welcome now equals "hello there"
```

### String Interpolation

String interpolation is a way to construct a new String value from a mix of constants, variables, literals, and expressions by including their values inside a string literal. Each item that you insert into the string literal is wrapped in a pair of parentheses, prefixed by a backslash (\):

```swift
let multiplier = 3
let message = "\(multiplier) times 2.5 is \(Double(multiplier) * 2.5)"
// message is "3 times 2.5 is 7.5"
```

### Accessing and Modifying a String

#### String Indices

Use the startIndex property to access the position of the first Character of a String. The endIndex property is the position after the last character in a String. 

You can use subscript syntax to access the Character at a particular String index.

```swift
let greeting = "Guten Tag!"
greeting[greeting.startIndex]
// G
greeting[greeting.index(before: greeting.endIndex)]
// !
greeting[greeting.index(after: greeting.startIndex)]
// u
let index = greeting.index(greeting.startIndex, offsetBy: 7)
greeting[index]
// a
```

#### Substrings

When you get a substring from a string—for example, using a subscript or a method like prefix(_:)—the result is an instance of `Substring`, not another string. 

```swift
let greeting = "Hello, world!"
let index = greeting.firstIndex(of: ",") ?? greeting.endIndex
let beginning = greeting[..<index]
// beginning is "Hello"

// Convert the result to a String for long-term storage.
let newString = String(beginning)
```

![Substring & String](./stringSubstring.png)

### String Operations

|Operations|Meaning|Example|
|---|---|---|
|isEmpty| A Boolean value indicating whether a string has no characters. | var a = "Hello, playground" <br> a.isEmpty|
|hasPrefix(prefix: String)| To check whether a string has a particular string prefix. | var a = "Hello, playground" <br> a.hasPrefix(prefix:"Hello")|
|hasSuffix(suffix: String)| To check whether a string has a particular string suffix. | var a = "Hello, playground" <br> a.hasSuffix(prefix:"d")|
|Int(String)| To convert a string into an Int if possible | let myString: String = "256" <br> let myInt: Int? = Int(myString)|
|count| The number of characters in a string. | var a = "Hello, playground" <br> print(a.count) |
|+| To concatenate two strings to get a new string | var a = "Hello, " <br> let b = "playground" <br> print(a + b) |
|+=| To concatenate two strings and assign the new value to the variable at the left side | var a = "Hello, " <br> a += "playground" <br> print(a) |
|==| To check if two strings are equal |  var a = "Hello, " <br> let b = "Hallo, " <br> print(a == b) |
|!=| To check if two strings are not equal |  var a = "Hello, " <br> let b = "Hallo, " <br> print(a != b) |
|<| Returns true if the left string is alpha-numerically smaller than the right string. Comparision starts from the first character to the last. |  var a = "Hello, " <br> let b = "Hallo, " <br> print(a < b) |







