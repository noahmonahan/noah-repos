**Task 2 - Host Discovery - Who is Online?**

*Q: What is the last IP address that will be scanned when your scan target is 192.168.0.1/27?*

A: To find this out, firstly we will run an nmap list scan of the target IP address. To do this, we will enter the following command: 
![alt text](<Images/nmap-fig1.png>)

After the scan has completed, it should look something like the following image: 

![alt text](<Images/nmap-fig2.png>)


Although nmap found 32 unique IP addresses on the subnet, keep in mind it counds the IP ending in .0.0 as an IP address. Therefore our answer is 192.168.0.31.

**Task 3 - Port Scanning: Who is Listening**

*Q: How many TCP ports are open on the target system?*

A: In order to do this, we must add an option specifically looking for ports that complete the three-way handshake. We do this with the -sT option shortcut in nmap. 

![alt text](<Images/nmap-fig3.png>)


*Q: Find the listening web server on the IP Address and access it with your browser. What is the flag that appears on its main page?*

A: This part does not require the linux command line, but our web browser.  Through our previous nmap scan, notice that port 8080 is open. 

![alt text](<Images/nmap-fig4.png>)


This is an HTTP port, meaning there is likely a web server being hosted. Let's enter that IP into our web browser and see what happens.

![alt text](<Images/nmap-fig5.png>)


Once we open the page, the following flag appears in front of us in plaintext: **_THM{SECRET_PAGE_38B9P6}_**

**Task 4 - Version Detection: Extract More Information**

*Q: What is the name and detected version of the web server running on the IP Address?*

A: To find this out, we will be using another nmap option to our advantage. We will be using the
-sV option to detect the service and version of the host. Let's see what the nmap results are.

![alt text](<Images/nmap-fig6.png>)

As seen in the figure above, port 8008 has now given us more insight into what service and version is running on the open port. 

**Task 5 - How Fast is Fast?**

*Q: What is the non-numeric equivalent of -T4?*

A: -T aggressive. This answer is given to us by the folks at tryhackme through this handy table. see the figure below for more details. 
![alt text](<Images/nmap-fig7.png>)



**Task 6 - Output: Controlling What You See**

*Q: What option must you add to your nmap command to enable debugging?*

A: -d is our answer. This is pretty straightforward. the "d" in -d stands for debug, and provides more insight than a regular verbose scan would.

**Task 7 - Conclusion and Summary**

*Q: What kind of scan will nmap use if you nmap "IP Address" with local user privileges?*

A: Connect Scan.  If you run an nmap scan with sudo (superuser) privileges, it will default to a SYN scan, which only utilizes the first step of the three-way handshake. If you run it as a local user it, it will do the entire three-way handshake as part of the network map.

That's It! Thank you for reading.