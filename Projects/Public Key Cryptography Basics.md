**Task 2 - Common Use of Asymmetric Encryption**

*Q: In the analogy presented, what real object is analogous to the public key?*

A: The answer is the **Lock**. In the analogy provided to explain asymmetric encryption, Person A sends a box that is locked with a lock (public key) that only Person B has the key (private key) to open. The keys themselves for encryption are completely different, hence the asymmetric. 

**Task 3 - RSA**

*Q: Knowing that p = 4391 and q = 6659. What is n?*

A: n is the **product** (result of multiplication) of variables p and q. 4391 x 6659 = 29239669. 
Thus, **n = 29,239,669**. 

*Q2: Knowing that p = 4391 and q = 6659, what is ϕ(n)?*

A: ϕ(n) = n - p - q + 1. Let's fill this equation out.
ϕ(n) = 29239669 - 4391 - 6659 + 1.
Crunching numbers quickly, we will see that  **ϕ(n) = 29,228,620**.

**Task 4 - Diffie-Hellman Key Exchange**

*Q: Consider p = 29, g = 5, a = 12. What is A?*

A: Let's put this into an equation quickly.

A = g^a % p
A = 5^12 % 29
A = 244140625 % 29
A = 7

Therefore, public key A is 7.

*Q2: Consider p = 29, g = 5, b = 17. What is B?*

A: Same as before, equation time.

B = g^b % p
B = 5^17 % 29
B = 762939453125 % 29
B = 9

Therefore, public key B is 9.

*Q3: Knowing that p = 29, a = 12, and you have B from the second question, what is the calculated by Bob? (key = B^a mod p)*

A:  

key = B^a % p
key = 9^12 % 29
key =  282429536481 % 29
key = 24

Therefore, the key is 24.

*Q4: Knowing that p = 29, b = 17 and you have A from the first question, what is the key calculated by Alice? (key = A^b mod p)*

A:

key = A^b % p
key = 7^17 % 29
key = 232630513987207 % 29
key = 24

Therefore, the key is 24.

**Task 5 - SSH**

*Q: Check the SSH Private Key in **~/Public-Crypto-Basics/Task-5**. What algorithm does the key use?*

A:  To begin this task, we need to log in to the target machine via SSH. We can do this through the following command as seen in the figure below: 

![alt text](<Images/PKC Basics-fig1.png>)


For the password, we have to go back to task 1 to find the user account and password. The password is Tryhackme123! for the user account "user".

Time to navigate to the directly stated in the question. We do this with the CD command.
We can see that the private key is an RSA key based on the file name. 

![alt text](<Images/PKC Basics-fig2.png>)


**Task 6 Digital Signatures and Certificates**

*Q: What does a remote web server use to prove itself to the client?*

A: A remote web server would use a **Certificate** to prove itself to the client. The most common use for this is in the HTTPS Protocol.

*Q2: What would you use to get a free TLS certificate for your website?*

A: Let's Encrypt is a free service where you can get a free TLS certificate for domains you own.

**Task 7 - PGP and GPG**

*Q: Use GPG to decrypt the message in **~/Public-Crypto-Basics/Task-7**. What Secret word does the message hold?*

A:  The answer to this is quite simple. Firstly, we must navigate to the file path specified in the question. A quick cd command will get us there. We can see that there is a message.gpg file for us to look at. There is also a tryhackme.key file seen there as well! We need to import this first: 

![alt text](<Images/PKC Basics-fig3.png>)
 Now that we have the secret key imported into GP, let's decrypt it using the following command seen below: 
 
 ![alt text](<Images/PKC Basics-fig4.png>)

Congratulations, we're done! Thank you for reading.