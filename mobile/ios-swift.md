Swift
=====

In iOS you have to follow :sparkles: MVC.

`@IBOutlet` define variables that refer to UI elements so you can make changes to them.

`@IBAction` define functions that respond to UI events.

Values
--------------
Swift has _Type Inference_ but you can explicitly declare types with ```var varName : TypeName = [initial value]```

Swift doesn't do implicit type conversions. Use the syntax `TypeName(value to convert)`.
Constants are defined with `let` and don't need to be known at compile-time. They can be only assigned to once.

String interpolation syntax: wrap your values inside `\()`

Multi-line strings using triple `"""`:
```
let myLongString = """
Here is a really
long multi-line
String
"""
```
Arrays and Dictionaries use the `[]` syntax. You can have a trialing comma when defining it's values.

Array examples:

```
let emptyArray = [String]()
let arr = [1,2,3,]
```

Dictionary examples:
```
let emptyDictionary = [String: Float]()
let dict = ["a":1,"b":2,"c":3,]
```

**Optionals** are values of type `Optional<>` and can have a value or be `nil`. Indicated by writing a "?" after the type. 

**Guard** is like an "unless".

The `if let name = optionalName { }` form for "Optional Binding"  is only testing for the existence of a value within an optional. If the variable has a value then it is unwrapped into "name" and the body is executed. If the value is `nil` then the body is skipped. An `else` clause can be provided to execute some code when the optional is `nil`.

The `??` operator can be used to provide a default value if an optional is `nil`.

Control Flow
--------------
Conditionals: `if`, `switch`
Loops: `for-in`, `while`, `repeat-while`.

Paranthesis around the condition is optional but braces around the body are required.

**Optional Chaining**
`blah?.blah2?.blah()`

**Optional Binding**
`if let opt = blah?.blah2?.blah() { }`
opt will be nil if any part of the chain is nil

**Closures**
Using the `on` keyword

Completion handlers (passing functions as arguments)

Trailing closure syntax: `{() in }`

Typealias to give helpful names to types

What is `<-` operator? It's ObjectMapper's custom operator

**Protocols** are like "interfaces" in other languages. And **Delegates** are what implement protocols.
