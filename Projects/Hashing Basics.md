**Task 2 - Hash Functions**

*Q1: What is the SHA256 hash of the **passport.jpg** file in **~/Hashing-Basics/Task-2**?*

A: Firstly, we need to navigate over to the file path itself. It is given to us in the question. 
Next, we need to use a hash function to show us our hash. We are looking for a sha256 hash, so we will use the **sha256sum** command in the command line. 77148c6f605a8df855f2b764bcc3be749d7db814f5f79134d2aa539a64b61f02 is our answer.

![alt text](<Images/Hashing-fig1.png>)

*Q2: What is the output size in bytes of the MD5 hash function?*

A: The solution to this one is a bit more complicated. We will use the same process as above, but for an MD5 hash instead of sha256. This is done with the command **md5sum**. 

![alt text](<Images/Hashing-fig2.png>)

Now that we have the hash, we unfortunately need to count the amount of hex characters it spat out. Then, we divide that number by 2, and that is our answer. The total amount of hex characters in the hash is 32. Divided by 2, that is **16 bytes**.

*Q3: If you have an 8-bit hash output, how many possible hash values are there?*

A: The answer is **256**. This can be gotten to by finding the number of possible hash values through the following equation: 2^(number of bits). In our case, it would be 2^8, which is 256.

**Task 3 - Insecure Password Storage for Authentication**

*Q1: What is the 20th password in **rockyou.txt**?*

A: As sad of a password as it is, **qwerty** is our answer. A quick way to get to this result is to input the following command: **head -n 20 rockyou.txt**. It will only output the first 20 lines of the text file, and you can easily identify the last line as the data you are looking for.

![alt text](<Images/Hashing-fig3.png>)

**Task 4 - Using Hashing for Secure Password Storage**

*Q1: Manually check the hash "4c5923b6a6fac7b7355f53bfe2b8f8c1" using the rainbow table above.*

A: 
![alt text](<Images/Hashing-fig4.png>)

As seen in the rainbow table, the provided hash is the last value in our rainbow table. Thus, making our answer seen above in the password column.

*Q2: Crack the hash "5b31f93c09ad1d065c0491b764d04933" using an online tool.*

A: For an online tool, I personally like to use **hashes.com**. Simply put in the provided cash, and watch it work its magic. From the information the website provides, we can see its an MD5 hash, and that our plaintext value and our answer, is **tryhackme**.

![alt text](<Images/Hashing-fig5.png>)


*Q3: Should you encrypt passwords in password-verification systems? (Yea/Nay)*

A: **Nay**. The reason is a catch 22 of sorts. This is because sure, you could encrypt the password, but you would still need to secure the key and store it somewhere. What happens when the key falls into the wrong hands? Decryption, and now you're compromised. Thus, there is no real point to it and hashing it is better.

**Task 5 - Recognizing Password Hashes**

*Q1: What is the hash size in yescrypt?*

A: **256**. This value can be found through the manual provided in the module in linux, or simply google. The manual can be reviewed by using the **man yescrypt** command.

*Q2: What's the Hash-Mode listed for Cisco-ASA MD5?*

A: **2410**. The answer can be found on an incredibly useful website called the [Hashcat Example Hashes([example_hashes [hashcat wiki]](https://hashcat.net/wiki/doku.php?id=example_hashes))] page. Simply search via CTRL-F for Cisco-ASA.

![alt text](<Images/Hashing-fig6.png>)



*Q3: What hashing algorithm is used in Cisco-IOS if it starts with "$9$"?*

A: **scrypt** is out answer. Like the previous answer, it can be found on the website provided in the tryhackme room or in this document. Once again, look for the characters in the question and identify the hashing algorithm.

**Task 6 - Password Cracking**

*Q1: Use **hashcat** to crack the hash, **$2a$06$7yoU3Ng8dHTXphAg913cyO6Bjs3K5lBnwq5FJyA6d01pMSrddr1ZG** saved in **~/Hashing-Basics/Task-6/hash1-txt**.*

A: To begin, let's identify what kind of hash we are working with. Once again, let's go to that webpage. This time, we are going to search for the beginning of the hash to see what we can find. By doing this, we see the following: 

![alt text](<Images/Hashing-fig7.png>)

We see that the hash provided is most likely hashed via the blowfish algorithm. Now, we enter into the command line the following: **hashcat -m 3200 $2a$06$7yoU3Ng8dHTXphAg913cyO6Bjs3K5lBnwq5FJyA6d01pMSrddr1ZG /us
r/share/wordlists/rockyou.txt**. This will run hashcat specifying for the blowfish algorithm, with our given wordlist of rockyou.txt. After this runs, our answer is **85208520**.

*Q2: Use **hashcat** to crack the SHA2-256 hash, **9eb7ee7f551d2f0ac684981bd1f1e2fa4a37590199636753efe614d4db30e8e1**, saved in saved in **~/Hashing-Basics/Task-6/hash2-txt**.*

A: Like before, we will be using hashcat. This time we are also given an algorithm. Let's look it up.

![alt text](<Images/Hashing-fig8.png>)

We see that SHA2-256 is hash mode 1400. Let's run the script. After hashcat runs, we see that the password is **halloween**. 

![alt text](<Images/Hashing-fig9.png>)

*Q3: Use **hashcat** to crack the hash **$ 6 $ GQXVvW4EuM$ehD6jWiMsfNorxy5SINsgdlxmAEl3.yif0/c3NqzGLa0P.S7KRDYjycw5bnYkF5ZtB8wQy8KnskuWQS3Yr1wQ0** saved in **~/Hashing-Basics/Task-6/hash3.txt**.*

A: Same as before, but good practice! Let's identify that hash.

![alt text](<Images/Hashing-fig10.png>)

Like before, allow hashcat to run.

![alt text](<Images/Hashing-fig14.png>)

the answer, as seen in the screenshot is **spaceman**.

*Q4: Crack the hash **b6b0d451bbf6fed658659a9e7e5598fe**, saved in **~/Hashing-Basics/Task-6/hash4.txt**.*

A: This is more akin to the last question. We need to identify the hashing algorithm first. We can run this through a hash identified, as seen in this document.

![alt text](<Images/Hashing-fig11.png>)

The online tool identifies this hash as an MD5 hash. The decryption can be done right on the webpage as well. The final hash value in plaintext is **funforyou**.

**Task 7 - Hashing for Integrity Checking**

*Q1: What is the SHA256 hash if **libgcrypt-1.11.0.tar.bz2** found in **~/Hashing-Basics/Task-7**?*

A: Firstly, we need to navigate over to the specified directory. We do this through the cd command as per usual. Then we run the sha256sum command followed by the file specified to see the SHA256 hash of the file. After running the script, we see that the hash is **09120c9867ce7f2081d6aaa1775386b98c2f2f246135761aae47d81f58685b9c**. 

![alt text](<Images/Hashing-fig12.png>)

*Q2: What's the hashcat mode number for **HMAC-SHA512 (key = $pass)**?*

A: To find this answer, all we need to do is look up the provided algorithm for checking integrity. This can be done on the website once again: 

![alt text](<Images/Hashing-fig13.png>)

As seen in the table, our answer is **1750**.

**Task 8 - Conclusion**

*Q1: Use **base64** to decode **RU5jb2RlREVjb2RlCg== ** saved as **decode-this.txt** in **~/Hashing-Basics/Task-8**. What is the original word?*

A: base64 is different from hashing. This is **encoding**. We will need to decode this. We can do this by running the following command in command line: **base64 -d decode-this.txt** while in the provided directory. The answer will be decoded as **ENcodeDEcode**.

**Thank you for reading!**

