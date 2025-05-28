**Task 2 - Essential Concepts**

*Q1: What term allows you to run a code block multiple times as long as it is a condition?*

A: A **Loop** is a coding term that allows you to run code multiple times assuming it meets a certain condition. This is usually through a **For** statement or a **While** statement.

**Task 3 - JavaScript Overview**

*Q1: What is the code output if the value of x is changed to 10?*

A: This is relatively simple. See the code in JavaScript below.

![alt text](<Images/js-fig1.png>)

If we change x's value to 10 instead of 5, the result variable will change accordingly and do the math. The result will now change from 15 to **20**. Thus, our answer is 20.

*Q2: Is JavaScript a compiled or interpreted language?*

A: JavaScript is an **Interpreted** language. This means that the code is interpreted directly in the browser with prior compilation. This can be dangerous in the wrong hands.

**Task 4 - Integrating JavaScript in HTML**

*Q1: Which type of JavaScript integration places the code directly within the HTML document?*

A: **Internal** JavaScript integrations place code directly into an HTML document. When you open the HTML document, it will open in your web browser by default.

*Q2: Which method is better for reusing JS across multiple web pages?*

A: **External** JavaScript files are better for reuse. This allows for developers to create cleaner and more consistent web pages more easily. Due note that these files will end with the .JS file extension.

*Q3: What is the name of the external JS file that is being called by **external_test.html**?*

A: **thm_external.js** is being called by **external_test.html**. The ladder html file is looking for the js file to see if the web page is written and formatted in internal JavaScript, or external.

**Task 5 - Abusing Dialogue Functions**

*Q1: In the file **invoice.html**, how many times does the code show the alert Hacked?*

A: If we look at the file itself in a text editor such as **pluma**, we can see that the **for** loop runs a total of **five times**.

![alt text](<Images/js-fig2.png>)

The above **for** loop will run as long as the variable **i** is less than 5. Therefore, the loop will end and stop running once i equals 5. Keep in mind that the loop will run once when i equals zero as well!

*Q2: Which of the JS interactive elements should be used to display a dialogue box that asks the user for input?*

A: The **prompt** element in JavaScript will ask the user to input or "prompt" the user for input for the web page. 

*Q3: If the user enters Tesla, what value is stored in the carName = prompt("What is your car name?")> In the carName variable?*

A: If the user is prompted for input and they input **Tesla** as stated in the question, carName would equal what the user input. Thus, our answer is **Tesla**.

**Task 6 - Bypassing Control Flow Statements**

*Q1: What is the message displayed if you enter the age less than 18?*

A: We are looking for the second line of text here when we open the **age.html** file with our web browser. We need to input an age under 18 as well.

![alt text](<Images/js-fig3.png>)

Upon entering a number under 18, we are informed by the html file that we are a minor. Giving us our answer.

*Q2: What is the password for the user admin?*

A: To get to our answer, we need to do a bit of digging. First off, we know that the user we are looking for the password of is admin. So when we open the file in our browser, let's enter admin for our username. You can input whatever you'd like for the password, or nothing at all. It should say our login authentication failed, which is true. This is where the digging begins. We need to inspect the elements of this html page. To do this, right click anywhere on the page, and hit **'inspect element'**. 

![alt text](<Images/js-fig4.png>)

In this case, it just says **Inspect**. It means the same thing. Next. let's inspect the element we actually want to inspect. This can be done by clicking the little dashed box with an arrow in the top left of the web browser's console. 

![alt text](<Images/js-fig5.png>)

Once that is clicked, hover your mouse over the "Login Authentication" element of the page. From here, we see the JavaScript. We do actually see a script minimized there. Let's open it up.

![alt text](<Images/js-fig6.png>)

We see that the html file has the correct password cached inside the file itself in plaintext. This is incredibly insecure, and not advised! **ComplexPassword** is our answer.

**Task 7 - Exploring Minified Files**

*Q1: What is the aler message shown after running the file **hello.html**?*

A: As soon as we open the file, we are greeted with the alert that has our answer: **Welcome to THM** 
![alt text](<Images/js-fig7.png>)

*Q2: What is the value of the **age** variable in the following obfuscated code snippet?*

*age=0x1*0x247e+0x35*-0x2e+-0x1ae3;*

A: To deobfuscate this snippet of code, we are going to use an online tool called [Obfuscator.io Deobfuscator](https://obf-io.deobfuscate.io/))
When we are there, we will input the snippet, and hit deobfuscate.

![alt text](<Images/js-fig8.png>)

After deobfuscation, we can see that the **age** variable we were looking for actually equals **21**.

**Task 8 - Best Practices**

*Q1: Is it a good practice to blindly include JS in your code from any source (yea/nay)?*

A: It is **NOT** a good practice to do this. **NEVER** blindly include any sort of code from any source in your projects. Vet the source before you do so. There are always going to be bad actors around. 

**Thanks for reading!**
