Task 1. Identify network interfaces
In this task, you must identify the network interfaces that can be used to capture network packet data.

1. Command to identify the interfaces that are available:
- sudo ifconfig

returns:
analyst@8f4673d507a3:~$ sudo ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1460
        inet 172.17.0.2  netmask 255.255.0.0  broadcast 172.17.255.255
        ether 02:42:ac:11:00:02  txqueuelen 0  (Ethernet)
        RX packets 770  bytes 13757662 (13.1 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 361  bytes 40250 (39.3 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 136  bytes 16265 (15.8 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 136  bytes 16265 (15.8 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

2. Command to identify the interface options available for packet capture:
- sudo tcpdump -D

returns:
analyst@8f4673d507a3:~$ sudo tcpdump -D
1.eth0 [Up, Running]
2.any (Pseudo-device that captures on all interfaces) [Up, Running]
3.lo [Up, Running, Loopback]
4.nflog (Linux netfilter log (NFLOG) interface)
5.nfqueue (Linux netfilter queue (NFQUEUE) interface)

Task 2. Inspect the network traffic of a network interface with tcpdump
In this task, you must use tcpdump to filter live network packet traffic on an interface.

1. Filter live network packet data from the eth0 interface with tcpdump:
- sudo tcpdump -i eth0 -v -c 5

returns:
analyst@8f4673d507a3:~$ sudo tcpdump -i eth0 -v -c 5
tcpdump: listening on eth0, link-type EN10MB (Ethernet), capture size 262144 bytes
01:34:34.893450 IP (tos 0x0, ttl 64, id 26467, offset 0, flags [DF], proto TCP (6), length 59)
    8f4673d507a3.5000 > nginx-us-west1-c.c.qwiklabs-terminal-vms-prod-00.internal.46196: Flags [P.], cksum 0x5859 (incorrect -> 0xe89c), seq 49802146:49802153, ack 821054750, win 492, options [nop,nop,TS val 1057078628 ecr 2557130246], length 7
01:34:34.893717 IP (tos 0x0, ttl 63, id 27726, offset 0, flags [DF], proto TCP (6), length 52)
    nginx-us-west1-c.c.qwiklabs-terminal-vms-prod-00.internal.46196 > 8f4673d507a3.5000: Flags [.], cksum 0x9cf8 (correct), ack 7, win 503, options [nop,nop,TS val 2557130277 ecr 1057078628], length 0
01:34:34.894271 IP (tos 0x0, ttl 64, id 48066, offset 0, flags [DF], proto UDP (17), length 69)
    8f4673d507a3.53174 > metadata.google.internal.domain: 63065+ PTR? 2.0.22.172.in-addr.arpa. (41)
01:34:34.896810 IP (tos 0x0, ttl 63, id 0, offset 0, flags [none], proto UDP (17), length 140)
    metadata.google.internal.domain > 8f4673d507a3.53174: 63065 1/0/0 2.0.22.172.in-addr.arpa. PTR nginx-us-west1-c.c.qwiklabs-terminal-vms-prod-00.internal. (112)
01:34:34.897701 IP (tos 0x0, ttl 64, id 58406, offset 0, flags [DF], proto UDP (17), length 74)
    8f4673d507a3.48352 > metadata.google.internal.domain: 10689+ PTR? 254.169.254.169.in-addr.arpa. (46)
5 packets captured
6 packets received by filter
0 packets dropped by kernel


Activity: Capture your first packet
experiment
Lab
schedule
1 hour
universal_currency_alt
No cost
show_chart
Introductory
info
This lab may incorporate AI tools to support your learning.
Lab instructions and tasks
Activity overview
Scenario
Start your lab
Task 1. Identify network interfaces
Task 2. Inspect the network traffic of a network interface with tcpdump
Task 3. Capture network traffic with tcpdump
Task 4. Filter the captured packet data
Conclusion
End your lab
Activity overview
As a security analyst, it’s important to know how to capture and filter network traffic in a Linux environment. You’ll also need to know the basic concepts associated with network interfaces.

In this lab activity, you’ll perform tasks associated with using tcpdump to capture network traffic. You’ll capture the data in a packet capture (p-cap) file and then examine the contents of the captured packet data to focus on specific types of traffic.

Let’s capture network traffic!

Scenario
You’re a network analyst who needs to use tcpdump to capture and analyze live network traffic from a Linux virtual machine.

The lab starts with your user account, called analyst, already logged in to a Linux terminal.

Your Linux user's home directory contains a sample packet capture file that you will use at the end of the lab to answer a few questions about the network traffic that it contains.

Here’s how you’ll do this: First, you’ll identify network interfaces to capture network packet data. Second, you’ll use tcpdump to filter live network traffic. Third, you’ll capture network traffic using tcpdump. Finally, you’ll filter the captured packet data.

Disclaimer: For optimal performance and compatibility, it is recommended to use either Google Chrome or Mozilla Firefox browsers while accessing the labs.
Start your lab
You'll need to start the lab before you can access the materials. To do this, click the green “Start Lab” button at the top of the screen.

Lab Start button displayed.

After you click the Start Lab button, you will see a shell, where you will be performing further steps in the lab. You should have a shell like this:

Linux Terminal displayed.

When you have completed all the tasks, refer to the End your Lab section that follows the tasks for information on how to end your lab.

Task 1. Identify network interfaces
In this task, you must identify the network interfaces that can be used to capture network packet data.

Use ifconfig to identify the interfaces that are available:
sudo ifconfig
Copied!
This command returns output similar to the following:

eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1460
        inet 172.17.0.2  netmask 255.255.0.0  broadcast 172.17.255.255
        ether 02:42:ac:11:00:02  txqueuelen 0  (Ethernet)
        RX packets 784  bytes9379957 (8.9 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 683  bytes 56880 (55.5 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0 collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 400  bytes 42122 (041.1 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 400  bytes 42122 (041.1 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0 collisions 0
The Ethernet network interface is identified by the entry with the eth prefix.

So, in this lab, you'll use eth0 as the interface that you will capture network packet data from in the following tasks.

Use tcpdump to identify the interface options available for packet capture:
sudo tcpdump -D
Copied!
This command will also allow you to identify which network interfaces are available. This may be useful on systems that do not include the ifconfig command.

Click Check my progress to verify that you have completed this task correctly.

You have completed this task and used ifconfig and tcpdump to list the network interfaces in this machine.
Identify network interfaces

You have completed this task and used ifconfig and tcpdump to list the network interfaces in this machine.
Task 2. Inspect the network traffic of a network interface with tcpdump
In this task, you must use tcpdump to filter live network packet traffic on an interface.

Filter live network packet data from the eth0 interface with tcpdump:
- sudo tcpdump -i eth0 -v -c5
This command will run tcpdump with the following options:

-i eth0: Capture data specifically from the eth0 interface.
-v: Display detailed packet data.
-c5: Capture 5 packets of data.
Now, let's take a detailed look at the packet information that this command has returned.

Some of your packet traffic data will be similar to the following:

tcpdump: listening on eth0, link-type EN10MB (Ethernet), capture size 262144 bytes
10:57:33.427749 IP (tos 0x0, ttl 64, id 35057, offset 0, flags [DF], protot TCP (6), length 134)
  7acb26dc1f44.5000 > nginx-us-east1-c.c.qwiklabs-terminal-vms-prod-00.internal.59788: Flags [P.], cksum 0x5851 (incorrect > 0x30d3), seq 1080713945:1080714027, ack 62760789, win 501, options [nop,nop,TS val 1017464119 ecr 3001513453], length 82
10:57:33.427954 IP (tos 0x0, ttl 64, id 21812, offset 0, flags [DF], protot TCP (6), length 52)
  nginx-us-east1-c.c.qwiklabs-terminal-vms-prod-00.internal.59788 > 7acb26dc1f44.5000: Flags [.], cksum 0x9122 (correct), ack 82, win 510, options [nop,nop,TS val 3001513453 ecr 1017464119], length 0
2 packets captured
4 packets received by filter
0 packets dropped by kernel
The specific packet data in your lab may be in a different order and may even be for entirely different types of network traffic. The specific details, such as system names, ports, and checksums, will definitely be different. You can run this command again to get different snapshots to outline how data changes between packets.

Exploring network packet details
In this example, you’ll identify some of the properties that tcpdump outputs for the packet capture data you’ve just seen.

In the example data at the start of the packet output, tcpdump reported that it was listening on the eth0 interface, and it provided information on the link type and the capture size in bytes:
tcpdump: listening on eth0, link-type EN10MB (Ethernet), capture size 262144 bytes
On the next line, the first field is the packet's timestamp, followed by the protocol type, IP:
22:24:18.910372 IP
The verbose option, -v, has provided more details about the IP packet fields, such as TOS, TTL, offset, flags, internal protocol type (in this case, TCP (6)), and the length of the outer IP packet in bytes:
(tos 0x0, ttl 64, id 5802, offset 0, flags [DF], proto TCP (6), length 134)
The specific details about these fields are beyond the scope of this lab. But you should know that these are properties that relate to the IP network packet.

In the next section, the data shows the systems that are communicating with each other:
7acb26dc1f44.5000 > nginx-us-east1-c.c.qwiklabs-terminal-vms-prod-00.internal.59788:
By default, tcpdump will convert IP addresses into names, as in the screenshot. The name of your Linux virtual machine, also included in the command prompt, appears here as the source for one packet and the destination for the second packet. In your live data, the name will be a different set of letters and numbers.

The direction of the arrow (>) indicates the direction of the traffic flow in this packet. Each system name includes a suffix with the port number (.5000 in the screenshot), which is used by the source and the destination systems for this packet.

The remaining data filters the header data for the inner TCP packet:
Flags [P.], cksum 0x5851 (incorrect > 0x30d3), seq 1080713945:1080714027, ack 62760789, win 501, options [nop,nop,TS val 1017464119 ecr 3001513453], length 82
The flags field identifies TCP flags. In this case, the P represents the push flag and the period indicates it's an ACK flag. This means the packet is pushing out data.

The next field is the TCP checksum value, which is used for detecting errors in the data.

This section also includes the sequence and acknowledgment numbers, the window size, and the length of the inner TCP packet in bytes.

Click Check my progress to verify that you have completed this task correctly.

You have completed this task and used tcpdump to filter live network traffic.
Inspect network traffic with tcpdump

You have completed this task and used tcpdump to filter live network traffic.
Task 3. Capture network traffic with tcpdump
In this task, you will use tcpdump to save the captured network data to a packet capture file.

In the previous command, you used tcpdump to stream all network traffic. Here, you will use a filter and other tcpdump configuration options to save a small sample that contains only web (TCP port 80) network packet data.

1. Capture packet data into a file called capture.pcap:
- sudo tcpdump -i eth0 -nn -c9 'port 80' -w capture.pcap &

- i eth0: Capture data from the eth0 interface.
- nn: Do not attempt to resolve IP addresses or ports to names.This is best practice from a security perspective, as the lookup data may not be valid. It also prevents malicious actors from being alerted to an investigation.
- c9: Capture 9 packets of data and then exit.
port 80: Filter only port 80 traffic. This is the default HTTP port.
- w capture.pcap: Save the captured data to the named file.
- &: This is an instruction to the Bash shell to run the command in the background.

returns:
tcpdump: listening on eth0, link-type EN10MB (Ethernet), capture size 262144 bytes

2. Use curl to generate some HTTP (port 80) traffic:
- curl opensource.google.com

returns:
analyst@8f4673d507a3:~$ curl opensource.google.com
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://opensource.google/">here</A>.
</BODY></HTML>
analyst@8f4673d507a3:~$ 9 packets captured
10 packets received by filter
0 packets dropped by kernel
9 packets captured
10 packets received by filter
0 packets dropped by kernel

3. Verify that packet data has been captured:
- ls -l capture.pcap

returns:
analyst@8f4673d507a3:~$ ls -l capture.pcap
-rw-r--r-- 1 root root 1410 Dec 11 01:54 capture.pcap
[1]-  Done                    sudo tcpdump -i eth0 -nn -c9 port 80 -w capture.pcap
[2]+  Done                    sudo tcpdump -i eth0 -nn -c9 'port 80' -w capture.pcap

Task 4. Filter the captured packet data
In this task, use tcpdump to filter data from the packet capture file you saved previously.

1. Use the tcpdump command to filter the packet header data from the capture.pcap capture file:
- sudo tcpdump -nn -r capture.pcap -v

returns:
analyst@8f4673d507a3:~$ sudo tcpdump -nn -r capture2.pcap -v
reading from file capture2.pcap, link-type EN10MB (Ethernet)
01:57:38.653336 IP (tos 0x0, ttl 64, id 20793, offset 0, flags [DF], proto TCP (6), length 60)
    172.17.0.2.60742 > 74.125.197.102.80: Flags [S], cksum 0xbc25 (incorrect -> 0x27cb), seq 1562411313, win 32660, options [mss 1420,sackOK,TS val 2074189128 ecr 0,nop,wscale 6], length 0
01:57:38.654335 IP (tos 0x0, ttl 126, id 0, offset 0, flags [DF], proto TCP (6), length 60)
    74.125.197.102.80 > 172.17.0.2.60742: Flags [S.], cksum 0x6c90 (correct), seq 3930569149, ack 1562411314, win 65535, options [mss 1420,sackOK,TS val 2267811722 ecr 2074189128,nop,wscale 8], length 0
01:57:38.654361 IP (tos 0x0, ttl 64, id 20794, offset 0, flags [DF], proto TCP (6), length 52)
    172.17.0.2.60742 > 74.125.197.102.80: Flags [.], cksum 0xbc1d (incorrect -> 0x9935), ack 1, win 511, options [nop,nop,TS val 2074189129 ecr 2267811722], length 0
01:57:38.654433 IP (tos 0x0, ttl 64, id 20795, offset 0, flags [DF], proto TCP (6), length 137)
    172.17.0.2.60742 > 74.125.197.102.80: Flags [P.], cksum 0xbc72 (incorrect -> 0x07e9), seq 1:86, ack 1, win 511, options [nop,nop,TS val 2074189129 ecr 2267811722], length 85: HTTP, length: 85
        GET / HTTP/1.1
        Host: opensource.google.com
        User-Agent: curl/7.64.0
        Accept: */*

01:57:38.654619 IP (tos 0x0, ttl 126, id 0, offset 0, flags [DF], proto TCP (6), length 52)
    74.125.197.102.80 > 172.17.0.2.60742: Flags [.], cksum 0x96c4 (correct), ack 86, win 1051, options [nop,nop,TS val 2267811722 ecr 2074189129], length 0
01:57:38.656620 IP (tos 0x0, ttl 126, id 0, offset 0, flags [DF], proto TCP (6), length 600)
    74.125.197.102.80 > 172.17.0.2.60742: Flags [P.], cksum 0x3528 (correct), seq 1:549, ack 86, win 1051, options [nop,nop,TS val 2267811724 ecr 2074189129], length 548: HTTP, length: 548
        HTTP/1.1 301 Moved Permanently
        Location: https://opensource.google/
        X-Content-Type-Options: nosniff
        Server: sffe
        Content-Length: 223
        X-XSS-Protection: 0
        Date: Wed, 11 Dec 2024 01:52:32 GMT
        Expires: Wed, 11 Dec 2024 02:22:32 GMT
        Cache-Control: public, max-age=1800
        Content-Type: text/html; charset=UTF-8
        Age: 306

        <HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
        <TITLE>301 Moved</TITLE></HEAD><BODY>
        <H1>301 Moved</H1>
        The document has moved
        <A HREF="https://opensource.google/">here</A>.
        </BODY></HTML>
01:57:38.656631 IP (tos 0x0, ttl 64, id 20796, offset 0, flags [DF], proto TCP (6), length 52)
    172.17.0.2.60742 > 74.125.197.102.80: Flags [.], cksum 0xbc1d (incorrect -> 0x96c0), ack 549, win 503, options [nop,nop,TS val 2074189131 ecr 2267811724], length 0
01:57:38.657852 IP (tos 0x0, ttl 64, id 20797, offset 0, flags [DF], proto TCP (6), length 52)
    172.17.0.2.60742 > 74.125.197.102.80: Flags [F.], cksum 0xbc1d (incorrect -> 0x96be), seq 86, ack 549, win 503, options [nop,nop,TS val 2074189132 ecr 2267811724], length 0
01:57:38.658197 IP (tos 0x0, ttl 126, id 0, offset 0, flags [DF], proto TCP (6), length 52)
    74.125.197.102.80 > 172.17.0.2.60742: Flags [F.], cksum 0x9497 (correct), seq 549, ack 87, win 1051, options [nop,nop,TS val 2267811726 ecr 2074189132], length 0

2. Use the tcpdump command to filter the extended packet data from the capture.pcap capture file.
- sudo tcpdump -nn -r capture.pcap -X

returns:
analyst@8f4673d507a3:~$ sudo tcpdump -nn -r capture.pcap -X
reading from file capture.pcap, link-type EN10MB (Ethernet)
01:54:03.285965 IP 172.17.0.2.44214 > 74.125.197.139.80: Flags [S], seq 3082758511, win 32660, options [mss 1420,sackOK,TS val 2872651726 ecr 0,nop,wscale 6], length 0
        0x0000:  4500 003c bc9c 4000 4006 c203 ac11 0002  E..<..@.@.......
        0x0010:  4a7d c58b acb6 0050 b7bf 296f 0000 0000  J}.....P..)o....
        0x0020:  a002 7f94 bc4a 0000 0204 058c 0402 080a  .....J..........
        0x0030:  ab39 2fce 0000 0000 0103 0306            .9/.........
01:54:03.287153 IP 74.125.197.139.80 > 172.17.0.2.44214: Flags [S.], seq 3000814803, ack 3082758512, win 65535, options [mss 1420,sackOK,TS val 1826847761 ecr 2872651726,nop,wscale 8], length 0
        0x0000:  4500 003c 0000 4000 7e06 40a0 4a7d c58b  E..<..@.~.@.J}..
        0x0010:  ac11 0002 0050 acb6 b2dc ccd3 b7bf 2970  .....P........)p
        0x0020:  a012 ffff ba17 0000 0204 058c 0402 080a  ................
        0x0030:  6ce3 7c11 ab39 2fce 0103 0308            l.|..9/.....
01:54:03.287168 IP 172.17.0.2.44214 > 74.125.197.139.80: Flags [.], ack 1, win 511, options [nop,nop,TS val 2872651727 ecr 1826847761], length 0
        0x0000:  4500 0034 bc9d 4000 4006 c20a ac11 0002  E..4..@.@.......
        0x0010:  4a7d c58b acb6 0050 b7bf 2970 b2dc ccd4  J}.....P..)p....
        0x0020:  8010 01ff bc42 0000 0101 080a ab39 2fcf  .....B.......9/.
        0x0030:  6ce3 7c11                                l.|.
01:54:03.287216 IP 172.17.0.2.44214 > 74.125.197.139.80: Flags [P.], seq 1:86, ack 1, win 511, options [nop,nop,TS val 2872651727 ecr 1826847761], length 85: HTTP: GET / HTTP/1.1
        0x0000:  4500 0089 bc9e 4000 4006 c1b4 ac11 0002  E.....@.@.......
        0x0010:  4a7d c58b acb6 0050 b7bf 2970 b2dc ccd4  J}.....P..)p....
        0x0020:  8018 01ff bc97 0000 0101 080a ab39 2fcf  .............9/.
        0x0030:  6ce3 7c11 4745 5420 2f20 4854 5450 2f31  l.|.GET./.HTTP/1
        0x0040:  2e31 0d0a 486f 7374 3a20 6f70 656e 736f  .1..Host:.openso
        0x0050:  7572 6365 2e67 6f6f 676c 652e 636f 6d0d  urce.google.com.
        0x0060:  0a55 7365 722d 4167 656e 743a 2063 7572  .User-Agent:.cur
        0x0070:  6c2f 372e 3634 2e30 0d0a 4163 6365 7074  l/7.64.0..Accept
        0x0080:  3a20 2a2f 2a0d 0a0d 0a                   :.*/*....
01:54:03.287396 IP 74.125.197.139.80 > 172.17.0.2.44214: Flags [.], ack 86, win 1051, options [nop,nop,TS val 1826847761 ecr 2872651727], length 0
        0x0000:  4500 0034 0000 4000 7e06 40a8 4a7d c58b  E..4..@.~.@.J}..
        0x0010:  ac11 0002 0050 acb6 b2dc ccd4 b7bf 29c5  .....P........).
        0x0020:  8010 041b e44b 0000 0101 080a 6ce3 7c11  .....K......l.|.
        0x0030:  ab39 2fcf                                .9/.
01:54:03.288547 IP 74.125.197.139.80 > 172.17.0.2.44214: Flags [P.], seq 1:548, ack 86, win 1051, options [nop,nop,TS val 1826847762 ecr 2872651727], length 547: HTTP: HTTP/1.1 301 Moved Permanently
        0x0000:  4500 0257 0000 4000 7e06 3e85 4a7d c58b  E..W..@.~.>.J}..
        0x0010:  ac11 0002 0050 acb6 b2dc ccd4 b7bf 29c5  .....P........).
        0x0020:  8018 041b 570c 0000 0101 080a 6ce3 7c12  ....W.......l.|.
        0x0030:  ab39 2fcf 4854 5450 2f31 2e31 2033 3031  .9/.HTTP/1.1.301
        0x0040:  204d 6f76 6564 2050 6572 6d61 6e65 6e74  .Moved.Permanent
        0x0050:  6c79 0d0a 4c6f 6361 7469 6f6e 3a20 6874  ly..Location:.ht
        0x0060:  7470 733a 2f2f 6f70 656e 736f 7572 6365  tps://opensource
        0x0070:  2e67 6f6f 676c 652f 0d0a 582d 436f 6e74  .google/..X-Cont
        0x0080:  656e 742d 5479 7065 2d4f 7074 696f 6e73  ent-Type-Options
        0x0090:  3a20 6e6f 736e 6966 660d 0a53 6572 7665  :.nosniff..Serve
        0x00a0:  723a 2073 6666 650d 0a43 6f6e 7465 6e74  r:.sffe..Content
        0x00b0:  2d4c 656e 6774 683a 2032 3233 0d0a 582d  -Length:.223..X-
        0x00c0:  5853 532d 5072 6f74 6563 7469 6f6e 3a20  XSS-Protection:.
        0x00d0:  300d 0a44 6174 653a 2057 6564 2c20 3131  0..Date:.Wed,.11
        0x00e0:  2044 6563 2032 3032 3420 3031 3a35 323a  .Dec.2024.01:52:
        0x00f0:  3332 2047 4d54 0d0a 4578 7069 7265 733a  32.GMT..Expires:
        0x0100:  2057 6564 2c20 3131 2044 6563 2032 3032  .Wed,.11.Dec.202
        0x0110:  3420 3032 3a32 323a 3332 2047 4d54 0d0a  4.02:22:32.GMT..
        0x0120:  4361 6368 652d 436f 6e74 726f 6c3a 2070  Cache-Control:.p
        0x0130:  7562 6c69 632c 206d 6178 2d61 6765 3d31  ublic,.max-age=1
        0x0140:  3830 300d 0a43 6f6e 7465 6e74 2d54 7970  800..Content-Typ
        0x0150:  653a 2074 6578 742f 6874 6d6c 3b20 6368  e:.text/html;.ch
        0x0160:  6172 7365 743d 5554 462d 380d 0a41 6765  arset=UTF-8..Age
        0x0170:  3a20 3931 0d0a 0d0a 3c48 544d 4c3e 3c48  :.91....<HTML><H
        0x0180:  4541 443e 3c6d 6574 6120 6874 7470 2d65  EAD><meta.http-e
        0x0190:  7175 6976 3d22 636f 6e74 656e 742d 7479  quiv="content-ty
        0x01a0:  7065 2220 636f 6e74 656e 743d 2274 6578  pe".content="tex
        0x01b0:  742f 6874 6d6c 3b63 6861 7273 6574 3d75  t/html;charset=u
        0x01c0:  7466 2d38 223e 0a3c 5449 544c 453e 3330  tf-8">.<TITLE>30
        0x01d0:  3120 4d6f 7665 643c 2f54 4954 4c45 3e3c  1.Moved</TITLE><
        0x01e0:  2f48 4541 443e 3c42 4f44 593e 0a3c 4831  /HEAD><BODY>.<H1
        0x01f0:  3e33 3031 204d 6f76 6564 3c2f 4831 3e0a  >301.Moved</H1>.
        0x0200:  5468 6520 646f 6375 6d65 6e74 2068 6173  The.document.has
        0x0210:  206d 6f76 6564 0a3c 4120 4852 4546 3d22  .moved.<A.HREF="
        0x0220:  6874 7470 733a 2f2f 6f70 656e 736f 7572  https://opensour
        0x0230:  6365 2e67 6f6f 676c 652f 223e 6865 7265  ce.google/">here
        0x0240:  3c2f 413e 2e0d 0a3c 2f42 4f44 593e 3c2f  </A>...</BODY></
        0x0250:  4854 4d4c 3e0d 0a                        HTML>..
01:54:03.288555 IP 172.17.0.2.44214 > 74.125.197.139.80: Flags [.], ack 548, win 503, options [nop,nop,TS val 2872651728 ecr 1826847762], length 0
        0x0000:  4500 0034 bc9f 4000 4006 c208 ac11 0002  E..4..@.@.......
        0x0010:  4a7d c58b acb6 0050 b7bf 29c5 b2dc cef7  J}.....P..).....
        0x0020:  8010 01f7 bc42 0000 0101 080a ab39 2fd0  .....B.......9/.
        0x0030:  6ce3 7c12                                l.|.
01:54:03.290301 IP 172.17.0.2.44214 > 74.125.197.139.80: Flags [F.], seq 86, ack 548, win 503, options [nop,nop,TS val 2872651730 ecr 1826847762], length 0
        0x0000:  4500 0034 bca0 4000 4006 c207 ac11 0002  E..4..@.@.......
        0x0010:  4a7d c58b acb6 0050 b7bf 29c5 b2dc cef7  J}.....P..).....
        0x0020:  8011 01f7 bc42 0000 0101 080a ab39 2fd2  .....B.......9/.
        0x0030:  6ce3 7c12                                l.|.
01:54:03.290477 IP 74.125.197.139.80 > 172.17.0.2.44214: Flags [F.], seq 548, ack 87, win 1051, options [nop,nop,TS val 1826847764 ecr 2872651730], length 0
        0x0000:  4500 0034 0000 4000 7e06 40a8 4a7d c58b  E..4..@.~.@.J}..
        0x0010:  ac11 0002 0050 acb6 b2dc cef7 b7bf 29c6  .....P........).
        0x0020:  8011 041b e220 0000 0101 080a 6ce3 7c14  ............l.|.
        0x0030:  ab39 2fd2                                .9/.
