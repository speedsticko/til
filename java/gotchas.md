**SimpleDateFormat** is not thread-safe so don't keep static instances that are being re-used.

Using immutable objects can help overcome some tricky shared object usages scenarios with worker threads.
