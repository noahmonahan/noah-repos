**Task 2 - Using Hydra**

*Q1: Use Hydra to bruteforce molly's web password. What is flag 1?*

A: Its time to use hydra to crack some passwords! We are going to enter the following into the Linux command line: 

*hydra -l molly -P /root/Tools/wordlists/rockyou.txt http-post-form "/:username=^USER^&password=^PASS^:F-incorrect" -V. 

Let Hydra run. It may take a little bit. Bruteforcing requires a fair amount of processing power. You can also add *-t x* to the end of the command, where x is the number of threads you would like to bruteforce in parallel. 

**`2673a7dd116de68e85c48ec0b1f2612e`** is our answer once we connect to the website, and login using molly's credentials which is our target.

![alt text](<Images/hydra-fig1.png>)

*Q2: Use Hydra to bruteforce molly's SSH password. What is flag 2?*

A: Once again, time to use hydra. Let it run:

*hydra -l molly -P /root/Tools/wordlists/rockyou.txt -t 4 ssh*

Once it is run, time to connect via ssh, and read it out: 

![alt text](<Images/hydra-fig2.png>)
That's our answer! **Thanks for reading!**







