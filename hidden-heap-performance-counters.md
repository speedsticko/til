# Windows Performance Counters for measing Heap performance

While investigating potential some heap memory contention issues I stumbled upon a few posts about some hidden performance counters.
There are some useful heap performance counters like Heap Lock Contention that are only available if you turn on a registry key.

HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\PerfProc\Performance "DisplayHeapPerfObject"=dword:00000001

References:
[https://support.microsoft.com/en-us/kb/290639](https://support.microsoft.com/en-us/kb/290639)
[heap-performance-counters](http://askldjd.com/2011/03/22/heap-performance-counters/)
