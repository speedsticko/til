- Everything is a method call, and paranthesis are optional
- Symbols are like strings but immutable and written with as: **:symbol**
- Hashes can be created with the old syntax: **dictionary = { "one" => "uno", "two" => "dos", "three" => "tres" }***
  or the new syntax **dictionary = { one: "uno", two: "dos", three: "tres" }** BUT with the difference that the keys are symbols (even though they are specified as "symbol:" instead of ":symbol").
  For example, these two hashes are equivalent:
  ```
  { :one => "uno", :two => "dos", :three => "tres" }
  { one: "uno", two: "dos", three: "tres" }
  ```
