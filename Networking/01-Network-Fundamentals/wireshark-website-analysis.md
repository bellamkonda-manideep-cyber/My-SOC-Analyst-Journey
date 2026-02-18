# Wireshark Lab 1 – Website Traffic Analysis (google.com)

## Objective
The goal of this lab was to understand what actually happens at the network level when opening a website and to observe DNS, TCP handshake, and HTTPS traffic using Wireshark.

## Lab Setup
I installed Wireshark and started capturing packets on my active network interface (Wi-Fi). After starting the capture, I opened https://google.com in my browser and allowed the page to load completely before stopping the capture.

## Observations

### 1. DNS Activity
When I applied the "dns" filter, I observed that my system first sent DNS queries before establishing any TCP connection. This confirmed that the system needed to resolve the domain name into an IP address before communication could begin.
<img width="1868" height="306" alt="image" src="https://github.com/user-attachments/assets/2305c2c7-b637-4425-b969-cc968de5958d" />

### 2. Destination IP Resolution
From the DNS response, I found that google.com was resolved to the IP address:
142.251.43.132
<img width="1903" height="24" alt="google_dns_2" src="https://github.com/user-attachments/assets/6ec3f395-adcb-4ef2-aceb-615cda0cd234" />
This showed how domain names are translated into IP addresses for actual network communication.

### 3. TCP Handshake Analysis
After DNS resolution, I filtered the traffic using "tcp" and observed the TCP three-way handshake:
- SYN packet from client
- SYN-ACK from server
- ACK from client
<img width="1859" height="222" alt="google_dns_3" src="https://github.com/user-attachments/assets/88c4f3eb-4a5e-4d58-90f4-dd1cd553bdcd" />

This confirmed that a reliable connection was established before data transfer.

### 4. HTTPS and Port Analysis
When analyzing the packets, I observed that the communication was happening over port 443, which indicates HTTPS traffic. The packets were encrypted (TLS), meaning the actual content could not be read in Wireshark.
<img width="1863" height="29" alt="google_dns_4" src="https://github.com/user-attachments/assets/5e87b883-d0b6-48e5-a7fd-99046ade952e" />

## Key Learning
This lab helped me understand that opening a website is not a single action but a sequence of network events:
DNS → TCP Handshake → TLS Encryption → Data Transfer.

I also learned how to identify protocols, ports, and packet flow using Wireshark, which is an essential skill for SOC analysts and cyber defenders.
