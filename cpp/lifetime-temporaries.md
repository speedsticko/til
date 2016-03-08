```
A temporary bound to a reference parameter in a function call (5.2.2) persists until the completion of the full expression containing the call
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
