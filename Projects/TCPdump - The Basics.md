
**Task 1: Introduction** 

*Q: What is the name of the library that is associated with tcpdump?*

A: libpcap is the answer. It is written in C and C++, and were released for Unix-like sysytems in the late 1980s/early 1990s (Cred. tryhackme.com).

**Task 2: Basic Packet Capture**

*Q: What option can you add to your command to display addresses only in numeric format?*

A: tcpdump -n will not resolve IP addresses in your packet capture.

![alt text](<Images/Tcpdump-fig1.png>)

**Task 3: Filtering Expressions**

*Q: How many packets in the **traffic.pcap** use the ICMP protocol?*

A: 26 packets. This number can be retrieved by entering the following into the command line.

![alt text](<Images/Tcpdump-fig2.png>)

To break it down, tcpdump is the actual command we are executing here. We are telling it to inspect packets. -r is the shortcut for us to read from a file for our packet inspection. The file in question is **traffic.pcap**. Next, we put in the parameter icmp to indicate we want to use icmp (Internet Control Messaging Protocol). Lastly, we pipe out and enter wc (wildcard) at the end to count the number of lines coming back at us (packets), to get out answer of 26 packets.

*Q: What is the IP address of the host that asked for the MAC address of 192.168.124.137?*

A: The answer is 192.168.124.148. Let's take this further.

![alt text](<Images/Tcpdump-fig3.png>)

Once again, we will be using the tcpdump command, followed by the -r and traffic.pcap file. The key difference here is what protocol we are using to resolve the request. Instead of ICMP, we will be using ARP (Address Resolution Protocol). This will allow us to see what machine has the IP we have and see the MAC address of the machine. Lastly, we enter the host IP address so we can tell ARP where to go. This will give us our answer.

*Q: What hostname (subdomain) appears in the first DNS query?*

A: mirrors.rockylinux.org

![alt text](<Images/Tcpdump-fig4.png>)

In order to get this answer, like usual, we call upon our trusty file, traffic.pcap. This time, we are specifying our search for port 53, which is the designated port for DNS queries. This returns us with our answer of mirrors.rockylinux.org.

**Task 4: Advanced Filtering**

*Q: How many packets have only the TCP Reset (RST) flag set?*

A: 57 packets. This can be achieved using the command seen below. We enter very specific search parameters to narrow down our search, and the list them all afterwards. tcp-rst is what we are looking for specifically here, so that is what came back to us.

![alt text](<Images/Tcpdump-fig5.png>)

*Q: What is the IP address of the host that sent packets larger than 15000 bytes?*

A: In the following query, we are going to be filtering via size. We do this with the parameter 'grater 15000' in our case. This will give us the packets we are looking for, as well as a source IP which is **185.117.80.53**.

![alt text](<Images/Tcpdump-fig6.png>)

**Task 5: Displaying Packets**

*Q: What is the MAC address of the host that sent an ARP request?*

A: ![alt text](<Images/Tcpdump-fig7.png>)

**52:54:00:7C:D3:5B** is our MAC address. This can be retrieved through the command line request seen above. The question states that the machine made an ARP request, so we can specify for that in our query. After that we use -e to specify we are looking for a MAC address, which is seen in our results here.

That's It! Thanks for reading!