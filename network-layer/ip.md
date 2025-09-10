# Internet Protocol

RFC 791 describes the fundamental aspects of the Internet Protocol (IP), which serves as the network layer for the Internet, enabling the interconnection of different networks and the use of hierarchical IP addressing. The later version, IP version 6 (IPv6), is defined in RFC 2460. 

The two primary responsibilities of IP are:

**Addressing**: IP assigns a unique numerical label, called an IP address, to every device connected to a network (like your computer, phone, or smart TV). This address acts like a mailing address, specifying exactly where the data should go.


**Routing**: IP takes large chunks of data and breaks them into smaller pieces called packets. It then sends these packets from the source device to the destination device. The packets travel across the internet by being passed from one router to another, with each router making a decision about the best path to send the packet along its journey.


## Versions: IPv4 vs. IPv6

IPv4: 4 bytes, IPv6: 16 bytes. IPv4: relies on manual configuration or a DHCP, IPv6: has SLAAC which allows devices to automatically create address w/o server. 

IPv6 doesn't need NAT.


## IPv4 Packet Format

```

0                   1                   2                   3  
0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|Version|  IHL  |Type of Service|          Total Length         |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|         Identification        |Flags|      Fragment Offset    |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|  Time to Live |    Protocol   |         Header Checksum       |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|                       Source Address                          |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|                    Destination Address                        |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|                    Options (if any)                           |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|                    Data (Payload)                             |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+

Field Descriptions
------------------
- Version: 4 bits, indicates IPv4 (value = 4).
- IHL (Internet Header Length): 4 bits, number of 32-bit words in the header.
- Type of Service (ToS): 8 bits, QoS parameters.
- Total Length: 16 bits, total packet size (header + data).
- Identification: 16 bits, unique ID for fragmentation.
- Flags: 3 bits, control fragmentation.
- Fragment Offset: 13 bits, position of fragment in the original packet.
- Time to Live (TTL): 8 bits, maximum hops before discard.
- Protocol: 8 bits, indicates upper-layer protocol (e.g., TCP=6, UDP=17).
- Header Checksum: 16 bits, error-checking for header.
- Source Address: 32 bits, sender IP address.
- Destination Address: 32 bits, receiver IP address.
- Options: Variable length (optional).
- Data: Payload carried by the packet.
```
