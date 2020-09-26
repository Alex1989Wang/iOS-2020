# Session 3

Key points covered in session 3. 

## Control Flow

Swift provides a variety of control flow statements. These include while loops to perform a task multiple times; if, guard, and switch statements to execute different branches of code based on certain conditions; and statements such as break and continue to transfer the flow of execution to another point in your code.

### Conditional Statements

#### If

Typically, you use the if statement to evaluate simple conditions, especially when the conditions can be expressed in true or false.  

```swift
temperatureInFahrenheit = 90
if temperatureInFahrenheit <= 32 {
    print("It's very cold. Consider wearing a scarf.")
} else if temperatureInFahrenheit >= 86 {
    print("It's really warm. Don't forget to wear sunscreen.")
} else {
    print("It's not that cold. Wear a t-shirt.")
}
```

#### Switch

A switch statement considers a value and compares it against several possible matching patterns.  The switch statement is better suited Enums are involved. 

```swift
switch `some_value_to_consider` {
case value_1:
    respond to value 1
case value_2, value_3:
    respond to value 2 or 3
default:
    otherwise, do something else
}
```

### Loops

#### For-In Loops

You use the for-in loop to iterate over a sequence, such as items in an array, ranges of numbers, or characters in a string.

```swift
for index in 1...5 {
    print("\(index) times 5 is \(index * 5)")
}
// 1 times 5 is 5
// 2 times 5 is 10
// 3 times 5 is 15
// 4 times 5 is 20
// 5 times 5 is 25
```

#### While Loops

##### while

```swift
while condition {
    statements
}
```

##### repeat-while

```swift
repeat {
    statements
} while condition
```

### Control Transfer Statements

- continue [loop]
- break [loop & switch]
- fallthrough [switch]
- return [loop & switch]
- throw [loop & swtich]

#### Continue

The continue statement tells a loop to stop what it is doing and start again at the beginning of the next iteration through the loop.

```swift
//print even numbers

```

#### Break

The break statement ends execution of an entire control flow statement immediately. 

### Early Exit

A guard statement, like an if statement, executes statements depending on the Boolean value of an expression. You use a guard statement to require that a condition must be true in order for the code after the guard statement to be executed. Unlike an if statement, a guard statement always has an else clause—the code inside the else clause is executed if the condition is not true.

```swift
guard some_condition else {
    else_statements
}

condition_true_statements

```

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

