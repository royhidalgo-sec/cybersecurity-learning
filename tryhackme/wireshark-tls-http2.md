# Wireshark — TLS Decryption & HTTP/2 Analysis

## Overview

In this lab, I analysed a `.pcapng` network capture using Wireshark.

The traffic was protected with **TLS 1.3**, so the application data could not initially be read directly. The browser had been configured to log its TLS session keys, allowing Wireshark to decrypt the captured traffic.

The objective was to analyse the decrypted traffic and locate the login credentials contained in one of the packets.

---

## Tools

* Wireshark
* Chromium
* TLS key log file (`ssl-key.log`)
* `.pcapng` packet capture

---

## 1. Loading the Packet Capture

The provided capture file was:

```text
randy-chromium.pcapng
```

I opened it in Wireshark and initially observed TLS traffic.

Because the traffic was encrypted, the application-level information was not immediately visible.

---

## 2. TLS Key Logging

The browser had been launched with the following option:

```bash
chromium --ssl-key-log-file=~/ssl-key.log
```

This generated a file containing the TLS session keys:

```text
ssl-key.log
```

These keys can be used by Wireshark to decrypt the TLS sessions.

---

## 3. Configuring Wireshark

In Wireshark, I opened the TLS preferences and configured the **(Pre)-Master-Secret log filename** to point to:

```text
~/ssl-key.log
```

After applying the configuration, Wireshark was able to decrypt the TLS traffic.

This allowed me to inspect protocols and application-level data that were previously hidden inside encrypted TLS Application Data packets.

---

## 4. Analysing HTTP/2

After decrypting the traffic, I filtered the packets using:

```text
http2
```

This revealed HTTP/2 traffic including:

```text
HEADERS
DATA
SETTINGS
```

I inspected the HTTP/2 headers and found requests such as:

```text
:method: POST
:authority: accounts.google.com
:path: /listaccounts
```

At first, this was not enough to identify the credentials, so I continued analysing the HTTP/2 streams.

---

## 5. Finding the Login Traffic

I searched the decrypted traffic for:

```text
login
```

This led me to an HTTP/2 stream containing relevant login-related traffic.

The stream had the following identifier:

```text
Stream ID: 15
```

I isolated the stream using:

```text
http2.streamid == 15
```

This made it easier to inspect the individual HTTP/2 frames belonging to that conversation.

---

## 6. Finding the Flag

By inspecting the decrypted HTTP/2 traffic and its `DATA` frames, I located the login-related information and eventually found the flag.

The important lesson was that the credentials were not directly visible while the TLS traffic was encrypted. Once the browser's TLS session keys were provided to Wireshark, the underlying HTTP/2 traffic could be analysed.

**Flag:**

```text
[REDACTED]
```

---

## Key Takeaways

* TLS encrypts application-layer traffic, making packet inspection difficult without the appropriate session keys.
* Browsers can log TLS session keys using the `--ssl-key-log-file` option.
* Wireshark can use these keys to decrypt captured TLS sessions.
* HTTP/2 uses streams identified by **Stream IDs**.
* Filtering with `http2.streamid == 15` allowed me to focus on one specific HTTP/2 conversation.
* `HEADERS` frames contain HTTP/2 metadata such as the method and path.
* `DATA` frames can contain the actual application data.

### Useful Wireshark filters

```text
http2
```

```text
http2.streamid == 15
```

Searching for relevant strings such as:

```text
login
password
username
```

can also help identify interesting traffic after decryption.

---

## What I Learned

This was my first lab where I had to investigate encrypted network traffic and use TLS session keys to reveal the underlying communication.

The main challenge was understanding that the information I was looking for was not necessarily in a single obvious packet. I had to follow the HTTP/2 conversation and identify the relevant stream before finding the useful data.

**First successful packet-analysis lab completed. 🔥**
