---
layout: post
title: 'WireShark'
date: 2024-10-30 09:16 -0800
categories: [Tutorials, Wireshark] 
tags: [Tutorials, Wireshark]
image:
  path: /assets/headers/wireshark-logo-big.png 
  lqip: 
---
  

#### **Wireshark**

Wireshark is a powerful network analyzer used to capture and inspect network traffic in real-time. It's commonly used for troubleshooting, performance analysis, and detecting security issues, providing detailed insights into network data.


Getting Started with Wireshark:

1. Download and Install: Get the latest version from Wireshark’s download page and install it using the default configuration.

2. Check Network Connection: Ensure your PC (with Wireshark installed) is physically connected to the network router.

3. Start Capturing:
- Open Wireshark, and double-click your network interface (e.g., Killer E2600 Gigabit Ethernet).
- Packets will be captured and displayed in real-time.

1. Stop and Save the Capture:
- Click the Stop button (RED square).
- Save the capture (e.g., FirstTraceFile.pcap) via File > Save.

1. Practice with Sample Captures: Download sample capture files like http.cap from the Wireshark Wiki Sample Captures.
- To open these files in Wireshark, go to File > Open.

>Wireshark is preinstalled with Kali Linux
{: .prompt-tip }


#### Resources

<ul>
  <li><a href="https://wiki.wireshark.org">Wireshark documentation as well as sample captures to disect</a></li> 
  <li><a href="https://www.wireshark.org/download.html">Wireshark - Download link</a></li>
</ul>

### Imporant Tips for getting started with Wireshark

Here are the top 5 most important things to know about Wireshark, with examples:

#### 1. **Filters (Capture vs. Display Filters)**
   - **Capture Filters**: Applied **before** packet capture, they limit the traffic that Wireshark collects (e.g., `port 80` to capture only HTTP traffic).
   - **Display Filters**: Applied **after** capture to refine the view of packets already collected (e.g., `ip.addr == 192.168.1.1` to show packets from/to a specific IP).
   - **Example**: To capture only HTTP traffic, use `tcp port 80` as a capture filter. Afterward, to see only traffic between two IPs, use `ip.src == 192.168.1.100 && ip.dst == 192.168.1.101` as a display filter.

#### 2. **Follow TCP/UDP Stream**
   - This feature allows you to see the complete conversation between two endpoints by reassembling packets into readable streams (useful for tracking web sessions or file transfers).
   - **Example**: Right-click on a TCP packet and choose **"Follow TCP Stream"** to view an entire HTTP conversation, such as a webpage load.

#### 3. **Protocol Analysis**
   - Wireshark supports over 2,000 network protocols. Understanding how to inspect key protocols (like TCP, DNS, HTTP) is essential.
   - **Example**: If you’re troubleshooting DNS issues, apply the filter `dns` and examine query/response packets to determine if the correct domain resolution is happening.

#### 4. **Statistics & Graphs**
   - Wireshark provides tools for analyzing packet timing, throughput, and protocol distribution, helping to spot network performance issues.
   - **Example**: Use **Statistics > I/O Graphs** to visualize traffic over time, identify peaks in bandwidth usage, or track packet delays.

#### 5. **Packet Details and Hex View**
   - Wireshark shows each packet’s layers (Ethernet, IP, TCP, etc.) with detailed breakdowns of headers and payloads. The Hex view helps in low-level inspection of packet contents.
   - **Example**: If you’re analyzing TCP connection problems, expand the TCP header in the packet details pane to check for flags like SYN/ACK, window size, or retransmissions.

Knowing these essentials will help you effectively analyze and troubleshoot network traffic using Wireshark.
   
## Youtube Videos
Chris Geer breaks it all down for you

{% include embed/youtube.html id='5PKAa6TI82U' %}

****





