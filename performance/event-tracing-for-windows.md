# Event Tracing for Windows

This is the most efficient way to adding event tracing to your Windows programs. 

To get a list of providers for Http related events:

```
logman query providers | findstr /i "Http"
```

Microsoft Message Analyzer (the successor to NetMon) is a good tool that can consume events and let you correlate events.
