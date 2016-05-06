
### Powershell Cmdlets
These cmdlets only work on Windows Server 2012.
- Get-NetTCPConnection
- Get-NetTCPSettings


### NetSh Show
- netsh interface tcp show global
- netsh interface tcp show heuristics

### NetSh Trace
You can quickly start start a ETW trace session on a machine with Win7 or newer using **netsh trace**

- netsh trace start
- netsh trace stop

netsh trace has the concept of scenarios and providers. Providers are ETW event providers and scenarios are pre-defined groupings of providers in a logical task oriented group. You can also add additional providers to a scenario.

### Netstat
- netstat -ab
To see which processes own which ports

### Tools
- Wireshark: can't sniff localhost
- Microsoft Message Analyzer

References:
- [Netsh Trace–Use It!](https://chentiangemalc.wordpress.com/2012/02/22/netsh-traceuse-it/)
- [Using Netsh to Manage Traces](https://msdn.microsoft.com/en-us/library/windows/desktop/dd569142(v=vs.85).aspx)
- [Capture a Network Trace without installing anything (& capture a network trace of a reboot)](https://blogs.msdn.microsoft.com/canberrapfe/2012/03/30/capture-a-network-trace-without-installing-anything-capture-a-network-trace-of-a-reboot/)
- [Built-In Trace Scenarios](https://technet.microsoft.com/en-us/library/jj659262.aspx)
