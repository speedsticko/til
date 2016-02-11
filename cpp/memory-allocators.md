### Memory Allocators

I watched an interesting [talk](https://www.youtube.com/watch?v=LIb3L4vKZ7U) by Andrei, [reddit](https://www.reddit.com/r/cpp/comments/3ollan/cppcon_2015_andrei_alexandrescu_stdallocator/) thread.

My main take-aways from the talk:
- main ideas in memory allocations pretty simple
- composition of allocators is a key design framework
- you can build up a lot of interesting allocator schemes. Some are useful for debugging and perf (AllocatorWithStats)
- std::allocator is flawed
- simplest useful allocator is the FallbackAllocator, with the typical fallback to malloc
- StackAllocator is simple and fast
