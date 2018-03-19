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

Multi line strings using triple `"""`:
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

Guard is like an "unless".

The `if let name = optionalName` form for "Optional Binding"  is only testing for the existence of a value within an optional.


Control Flow
--------------

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
