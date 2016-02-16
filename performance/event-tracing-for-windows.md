# Event Tracing for Windows

This is the most efficient way to adding event tracing to your Windows programs. 

To get a list of providers for Http related events:

```
logman query providers | findstr /i "Http"
```

To get the available events and their format:
```
wevtutil get-publisher Microsoft-Windows-WinInet /getevents /getmessage
```
You can also combine this with findstr to filter for specific events you're interested in:
```
wevtutil gp Microsoft-Windows-WinINet /ge /gm | findstr /i httpopen
```

Microsoft Message Analyzer (the successor to NetMon) is a good tool that can consume events and let you correlate events.


My sources:
- [Part 2 - Exploring and Decoding ETW Providers using Event Log Channels](http://blogs.msdn.com/b/ntdebugging/archive/2009/09/08/exploring-and-decoding-etw-providers-using-event-log-channels.aspx)
