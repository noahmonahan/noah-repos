**Task 2 - Web Application Overview**

*Q1: Which component on a computer is responsible for hosting and delivering content for web applications?*

A: A **Web Server** is responsible for hosting and delivering content for web applications. This is the main processing power of the website.

*Q2: Which tool is used to access and interact with web applications?*

A: A **Web Browser** is used by the end user on a home computer or mobile device to access and interact with websites and web applications on the world wide web.

*Q3: Which component acts as a protective layer, filtering incoming traffic to block malicious attacks, and ensuring the security of the web applications?*

A: A **WAF**, or **Web Application Firewall** acts as the protective layer for web servers. They filter and block out bad actors, and traffic.

**Task 3 - Uniform Resource Locator**

*Q1: Which protocol provides encrypted communication to ensure secure data transmission between a web browser and a web server?*

A: **HTTPS, or Hypertext Transmission Protocol (Secure)** is what allows a user to secure data transmission between a web browser and a web server. Regular HTTP is significantly less secured and is not advised to be used.

*Q2: *What term describes the practice of registering domain names that are misspelt variations of popular websites to exploit user errors and potentially engage in fraudulent activities?**

A: **Typosquatting** is a form of malicious attack where the attacker or instigator registers a domain that is incredibly similar to that of a popular website, where users will likely end up at simply due to a minor typo or spelling mistake in the **URL** they were typing.

*Q3: What part of a URL is used to pass additional information, such as search terms or form inputs to the web server?*

A: A **Query String** is the part of the URL that i used, and starts with a question mark (?), and its main purpose is usually for identifying search terms of form inputs.

**Task 4 - HTTP Messages**

*Q1: Which HTTP message is returned by the web server after processing a client's request?*

A: A **HTTP Response** is what a web server will return to the end user after processing their request.

*Q2: What follows the headers in an HTTP message?*

A: An **Empty Line** follows the header in an HTTP message. Its a divider that separates the header from the body of the HTTP message.

**Task 5 - HTTP Request: Request Line and Methods**

*Q1: Which HTTP protocol version became widely adopted and remains the most commonly used version for web communication, known for introducing features like persistent connections and chunked transfer encoding?*

A: **HTTP/1.1**, introduced in 1997, introduced the aforementioned features. There are more modern and newer versions, although 1.1 is still the most widely adopted.

*Q2: Which HTTP request method describes the communication options for the target resource, allowing clients to determine which HTTP methods are supported by the web server?*

A: The **OPTIONS** request will tell the user what methods are available for a specific resource, assisting the user in what they are able to do.

*Q3: In an HTTP request, which component specifies the specific resource or endpoint on the web server that the client is requesting, typically appearing after the domain name in the URL?*

A: The **URL Path**, which typically appears after the domain name in the URL, tells the web client specifically what part the user is attempting to access.

**Task 6 - HTTP Request: Headers and Body**

*Q1: Which HTTP request header specified the domain name of the web server to which the request is being sent?*

A: The **Host** request header is specified in the domain name of the web server to which the request is being sent.

*Q2: What is the default content type for form submissions in an HTTP request where the data is encoded as key=value pairs in a query string format?*

A: **application/x-www-form-urlencoded** is the default content type.

*Q3: Which part of an HTTP request contains additional information like host, user agent, and content type, guiding how the web server should process the request?*

A: **Request Headers** contain additional information that guides the web server processing the request initiated by the end user.

**Task 7 - HTTP Response: Status Line and Status Codes**

*Q1: What part of an HTTP response provides the HTTP version, status code, and a brief explanation of the response's outcome?*

A: The **Status Line** provides the HTTP version, status code, and brief explanation of the response from the web server, good, or bad.

*Q2: Which category of HTTP response codes indicates that the web server encountered an internal issue or is unable to fulfill the client's request?*

A: **Server Error Responses**, codes also known as codes found between **500 and 599** indicate that the server encountered an issue while trying to fulfill a request from a client.

*Q3: Which HTTP status code indicates that the requested resource could not be found on the web server?*

A: Error **404** indicates that the requested resource could not be found.

**Task 8 - HTTP Response: Headers and Body**

*Q1: Which HTTP response header can reveal information about the web server's software and version, potentially exposing it to security risks if not removed?*

A: The **Server** response header can reveal a lot information about a web server. Including the software it is running, as well as the version. This brings a lot of unnecessary security risks and is advised to be hidden.

*Q2: Which flag should be added to cookies in the Set-Cookie HTTP response header to ensure they are only transmitted over HTTPS, protecting them from being exposed during unencrypted transmissions?*

A The **Secure** flag will need to be utilized so that data in transit is encrypted and only transmitted over HTTPS, which is significantly more secure than standard HTTP.

*Q3: Which flag should be added to cookies in the Set-Cookie HTTP response header to prevent them from being accessed via JavaScript, thereby enhancing security against XSS attacks?*

A: The **HttpOnly** flag needs to be added to cookies in the Set-Cookie HTTP response header. This makes it so that JavaScript and other query languages cannot be used, resulting in fewer XSS attacks.

**Task 9 - Security Headers**

*Q1: In a Content Security Policy (CSP) configuration, which property can be set to define where scripts can be loaded from?*

A: **script-src**, short for script-source, defines where scripts can be loaded from, acting as a security measure.

*Q2: When configuring the Strict-Transport-Security (HSTS) header to ensure that all subdomains of a site also use HTTPS, which directive should be included to apply the security policy to both the main domain and its subdomains?*

A: The **inculdesubdomains** directive should be included in the HSTS header to ensure that all domains, including subdomains, can only use HTTPS, adding security.

*Q3: Which HTTP header directive is used to prevent browsers from interpreting files as a different MIME type than what is specified by the server, thereby mitigating content type sniffing attacks?*

A: The **nosniff** directive will tell the browser not to sniff or guess the MIME (Multipurpose Internet Mail Extension) type the web server is using.

**Task 10 - Practical Task: Making HTTP Requests**

*Q1: Make a GET request to /api/users. What is the flag?*

A: Firstly, we need to open the website linked in the exercise. It will give you a brief how-to on how to toggle certain functions and requests. Set HTTP to **GET**. Then, enter */api/users* at the end of the URL. This will return the correct response, and our flag:

![alt text](<Images/webapp-fig1.png>)

*Q2: Make a **POST** reuqest to /api/user/2 and update the **country** of Bob from UK to US. What is the flag?*

A: Like before, we need to be in the web browser provided. Now, we need to change our **GET** request to a **POST** request from the dropdown. Afterwards, we need to change the URL from */api/users* to */api/user/2*. Finally, click the gear in the top right. We need to change the parameters a little bit for our **POST** request to actually replace data.

![alt text](<Images/webapp-fig2.png>)

since we already specified in the URL that we are modifying Bob's data, this is changing the specifics. The key-value pair we are changing is Bob's country. So, the first value will be country, and the second will be US.

This will give you the key! 

*Q3: Make a **DELETE** request to /api/user/1 to delete the user. What is the flag?*

A: Still in the browser, we need to now change our **POST** request to a **DELETE** request. This can be done via the dropdown menu in the top left. Afterwards, we need to change the URL once again from */api/user/2* to */api/user/1*. Very simple, yet important change. Finally, hit go.

**Thank you for reading!**