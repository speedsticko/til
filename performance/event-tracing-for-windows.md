# Event Tracing for Windows

This is the most efficient way to adding event tracing to your Windows programs. 

Concepts
========
Provider
Consumsers
Tracing Session

To register a provider and schema:
```
wevtutil im provider.man
```

To unregister a provider and schema:
```
wevtutil um provider.man
```
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
- [.NET Event Tracing for Windows](http://blogs.msdn.com/b/dixi/archive/2009/04/23/net-event-tracing-for-windows.aspx)
