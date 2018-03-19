Swift
=====

In iOS you have to follow :sparkle: MVC.

`@IBOutlet` define variables that refer to UI elements so you can make changes to them.

`@IBAction` define functions that respond to UI events.

Guard is like an "unless".
 
The `if let name = optionalName` form for "Optional Binding"  is only testing for the existence of a value within an optional.

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
