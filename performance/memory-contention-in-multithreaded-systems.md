# Memory contention in multhreaded systems

### Problem
Memory contention occurs when a lot of threads are trying to do memory allocation/deallocations on the shared heap. 
Access to the shared heap must be protected with locks which can kill your performance if your threads are all trying to get memory.

### Solutions
Basic idea is to give each thread exclusive access to it's own big chunk of memory that it can allocate from. 
The trade offs here are performance, complexity, and memory efficiency.

There are multiple ways to accomplish this:
- Have each thread allocate a memory pool (or any big chunk of memory) at startup and make the thread allocate dynamically from there.
- On Windows you can allocate a per-thread Heap
- You can use Thread Local Storage to have a slot for a pointer to the memory pool

Alternatively, you can buy/get a thread-aware memory allocator. 
Or try to re-write your program so that it's memory allocations are done up-front or you can get away only with local variables. This will not always be possible.

Sources
[Dr Dobbs - Memory Constraints on Thread Performance](http://www.drdobbs.com/tools/memory-constraints-on-thread-performance/231300494)
[Intel - Avoiding Heap Contention Among Threads](https://software.intel.com/en-us/articles/avoiding-heap-contention-among-threads)
