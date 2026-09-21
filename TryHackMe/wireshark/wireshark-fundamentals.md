# Wireshark Fundamentals

Hands-on practice with Wireshark and network traffic analysis through TryHackMe.

## What I learned

* How to analyze PCAP and PCAPNG capture files
* How to inspect packet details and protocol layers
* How encapsulation appears in captured traffic
* How to identify and analyze network protocols
* How to search for specific strings inside packet details
* How to inspect HTTP traffic
* How to follow network traffic
* How to extract objects from HTTP traffic
* How to export packet bytes from individual packets
* How to calculate MD5 hashes for extracted files

## Practical techniques

### Search packet details

Wireshark can be used to search packet details for specific strings.

Example:

```text
Ctrl + F
Search In → Packet Details
Search For → String
```

### Export HTTP objects

HTTP objects can be extracted directly from a capture:

```text
File → Export Objects → HTTP
```

This can be useful when investigating files transferred through HTTP traffic.

### Export packet bytes

Individual packet contents can also be exported from the Packet Details pane when the relevant protocol/data section is identified.

### Calculate an MD5 hash

After extracting a file:

```bash
md5sum <filename>
```

This allows the extracted file's MD5 hash to be calculated and compared when required.

## Key takeaway

Wireshark makes it possible to move from high-level network traffic to individual packets and protocol fields, making it a valuable tool for understanding and investigating network communications.

## Skills practiced

`Wireshark` `PCAP Analysis` `Packet Analysis` `HTTP` `TCP` `UDP` `Network Protocols` `Traffic Analysis` `MD5`
