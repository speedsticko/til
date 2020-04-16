Your iOS normally operates in the foreground by when the user switches to something else, your app will quickly switch to the background state, and a little while later the OS can suspend your app (see iOS app life-cycle).
iOS has some features that allow you to extend the time you're in background mode and to let you perform some processing in the background.

Some notes from Quinn: https://forums.developer.apple.com/thread/85066
https://agostini.tech/2018/04/08/background-transfers-using-urlsession/

There are 4 main features you can use for different use-cases:

1. UIApplication beginBackgroundTask(withName:expirationHandler:) 

This tells the OS you want to extend your app's background execution time before it gets suspended. 
Normally when you app switches to the backgroundm your app  delegate's applicationDidEnterBackground(_:) gets called and you get about 5 seconds or execution time before your app gets suspended. With this you can get some more time to perform any critical operations to perserve your apps integrity, but not that much, about 30 seconds. You can get an estimate by reading the backgroundTimeRemaining property.

Reference: https://developer.apple.com/documentation/uikit/app_and_environment/scenes/preparing_your_ui_to_run_in_the_background/extending_your_app_s_background_execution_time

2. Background fetch

This lets your app perform some operation in a 30 minute window. When this happens is up to the OS.
The typical example use-case is say you have something like a Twitter-style app and you want to provide the user with updated data at the next launch.
You can fetch updated data while in the background (or suspended?).

3. Background URLSession

A seperate daemon process runs your download and upload tasks. When the tasks are completed your app is launched in the background to perform some housekeeping.
Since it's a seperate process the only way to share data in your tasks is through the file system (i.e. nsurlsessionsd can't access your app's memory).

Tips for testing from Quinn “The Eskimo!”: https://forums.developer.apple.com/thread/14855

4. Background processing (iOS 13+ only)

This lets you schedule tasks with the OS to be performed in the background for you.


Also, alamofire has trouble with background sessions.
