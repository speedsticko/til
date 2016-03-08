```
A temporary bound to a reference parameter in a function call (5.2.2) persists until the completion of the full expression containing the call
```

A temporary is **unnamed**. Which of the following is a temporary?
```
The rules that govern the lifetimes of temporary objects have nothing to do with notion of scope. Scope is a property of a name, and temporary objects do not have names. In other words, temporary objects have no scope.
```

```
AObject A();

vs

AObject(); // un-named

vs

auto obj = AObject();

vs 

Foo(AObject());

vs 

Foo(AObject().Val());

vs
AObject getAObject();
{
  const AObject& r = getAObject(); // full expression ends here
  ...
} // object returned by getAObject() is destroyed here

```
