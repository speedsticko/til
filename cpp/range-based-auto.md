# Range-based auto variable choices

Like many times in C++ there are many options available to you when you want to do something. 
When you want to iterate through some kind of collection, you have 4 choices on how to create the temporary iteration variable.
Here's how to decide which to use:

```
for(___ v : coll)
{
}
```

* auto v : coll - you want to make a copy and work with a copy
* auto& v : coll - you want to avoid a copy and you want to make changes to the element
* const auto& v : coll or auto& const v :coll - you want to avoid making a copy by using a reference and you don't want to make changes to the element
* auto&& v : coll - you want a r-value
