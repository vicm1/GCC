Task 1. Explore data with Wireshark
In this task, you must open a network packet capture file that contains data captured from a system that made web requests to a site. You need to open this data with Wireshark to get an overview of how the data is presented in the application.

1. What is the protocol of the first packet in the list where the info column starts with the words 'Echo (ping) request'?
- ICMP

Task 2. Apply a basic Wireshark filter and inspect a packet
In this task, you’ll open a packet in Wireshark for more detailed exploration and filter the data to inspect the network layers and protocols contained in the packet.

1. Enter the following filter for traffic associated with a specific IP address. Enter this into the Apply a display filter... text box immediately above the list of packets:
- ip.addr == 142.250.1.139

2. What is the TCP destination port of this TCP packet?
- 80

Task 3. Use filters to select packets
In this task, you’ll use filters to analyze specific network packets based on where the packets came from or where they were sent to. You’ll explore how to select packets using either their physical Ethernet Media Access Control (MAC) address or their Internet Protocol (IP) address.

1. Enter the following filter to select traffic for a specific source IP address only. Enter this into the Apply a display filter... text box immediately above the list of packets:
- ip.src == 142.250.1.139

2. Enter the following filter to select traffic for a specific destination IP address only:
- ip.dst == 142.250.1.139

3. Enter the following filter to select traffic to or from a specific Ethernet MAC address. This filters traffic related to one MAC address, regardless of the other protocols involved:
- eth.addr == 42:01:ac:15:e0:02

4. What is the protocol contained in the Internet Protocol Version 4 subtree from the first packet related to MAC address 42:01:ac:15:e0:02?
- TCP

Task 4. Use filters to explore DNS packets
In this task, you’ll use filters to select and examine DNS traffic. Once you‘ve selected sample DNS traffic, you’ll drill down into the protocol to examine how the DNS packet data contains both queries (names of internet sites that are being looked up) and answers (IP addresses that are being sent back by a DNS server when a name is successfully resolved).

1. Enter the following filter to select UDP port 53 traffic. DNS traffic uses UDP port 53, so this will list traffic related to DNS queries and responses only. Enter this into the Apply a display filter... text box immediately above the list of packets:
- udp.port == 53

2. Which of these IP addresses is displayed in the expanded Answers section for the DNS query for opensource.google.com?
- 142.250.1.139

Task 5. Use filters to explore TCP packets
In this task, you’ll use additional filters to select and examine TCP packets. You’ll learn how to search for text that is present in payload data contained inside network packets. This will locate packets based on something such as a name or some other text that is of interest to you.

1. Enter the following filter to select TCP port 80 traffic. TCP port 80 is the default port that is associated with web traffic
- tcp.port == 80

2. What is the Time to Live value of the packet as specified in the Internet Protocol Version 4 subtree?
- 64

3. What is the Frame Length of the packet as specified in the Frame subtree?
- 54 bytes

4. What is the Header Length of the packet as specified in the Internet Protocol Version 4 subtree?
- 20 bytes

5. What is the Destination Address as specified in the Internet Protocol Version 4 subtree?
- 169.254.169.254
