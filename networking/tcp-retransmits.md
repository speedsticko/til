# TCP Retransmissions

When a TCP packet isn't received it must be retransmitted. Obviously, this will hurt performance.

There are 2 main reasons for a re-transmission:
* Packet loss (either data or ACK) - unreliable network
* Congestion
- The receiver can't handle the data (for whatever reason) and does not ACK it
- The sender can't handle the ACK (for whatever reason) and then retransmits
