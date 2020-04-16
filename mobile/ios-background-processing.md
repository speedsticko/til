Your iOS normally operates in the foreground by when the user switches to something else, your app will quickly switch to the background state, and a little while later the OS can suspend your app (see iOS app life-cycle).
iOS has some features that allow you to extend the time you're in background mode and to let you perform some processing in the background.

There are 4 main features you can use for different use-cases:

1. Background task

This tells the OS you want to extend your app's background execution time before it gets suspended. Normally you get about 5 seconds or execution time.
With this you can get some more time to perform any critical operations to perserve your apps integrity.

2. Background fetch

This lets your app perform some operation in a 30 minute window. When this happens is up to the OS.
The typical example use-case is say you have something like a Twitter-style app and you want to provide the user with updated data at the next launch.
You can fetch updated data while in the background (or suspended?).

3. Background URLSession

A seperate daemon process runs your download and upload tasks. When the tasks are completed your app is launched in the background to perform some housekeeping.
Since it's a seperate process the only way to share data in your tasks is through the file system (i.e. nsurlsessionsd can't access your app's memory).

4. Background processing

This lets you schedule tasks with the OS to be performed in the background for you.
