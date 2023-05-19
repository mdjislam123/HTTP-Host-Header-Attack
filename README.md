# HTTP-Host-Header-Attack
This project was for the Computer Security and Forensics, Spring 2023 semester at John Jay College of Criminal Justice.

                                                              HTTP Vulnerability Analysis
                                                              
                                                               "HTTP Host Header Attack"
                                                               
                                                                          By
                                                                          
                                                                  Md Jayadul Islam
                                                                  
                                                              md.islam1@jjay.cuny.edu
                                                              
                                                                          For
                                                                          
                                                  CSCI-411 Computer Security and Forensics, Spring 2023
                                                  
                                                              Instructor: Professor Aftab Ahmad
                                                              
                           
                           
           The work reported in this document, including creating this report, was done by me, except were cited with the accompanying source 
           reference and permission if required by the source. No part of the report was produced by a non-human, software, or hardware. 
           Any exception to this statement can be considered a breach of academic integrity.
                                                                      
                                                                      Submitted on
                                                                      
                                                                     April 02, 2023
                                                                     
                                                      Department of Mathematics and Computer Science
                                                      
                                                            John Jay College of Criminal Justice
                                                            
                                                          524 West 59th Street, New York, NY 10019
                                                          
                                                          
                                                          

(K)nowledge:
Starting with the knowledge part of the report, I will learn the zero-day vulnerability of the HTTP protocol. However, before beginning writing, we need to know how the HTTP protocol works.
HTTP stands for Hypertext Transfer Protocol. It is an application protocol for transferring data over the web, most commonly used for accessing websites on the internet. HTTP sends requests from a client (such as a web browser) to a server, which then responds with data. The requests and responses are sent in a specific format that follows a set of rules and conventions outlined in the HTTP specification. For example, when a user enters a URL into their web browser, the browser sends an HTTP request to the server hosting that website. The server then responds with the website's HTML, CSS, JavaScript, and other files, which the browser interprets and displays to the user. But since this protocol was created, many vulnerabilities, exploits, and attacks have existed. As a consequence, users' accounts and personal information were breached.
HTTP vulnerabilities can occur due to flaws in the protocol's design, implementation, or configuration, which attackers can exploit to launch attacks. In the context of HTTP vulnerabilities, exploits are typically used to take advantage of weaknesses in the protocol implementation to achieve a specific goal. For example, an attacker could use an HTTP exploit to host header attack and gain unauthorized access to a web application or server. There are different HTTP exploits, including buffer overflows, authentication bypassing, cross-site scripting (XSS) attacks, DoS etc. Attacks using HTTP exploits can have a wide range of consequences, depending on the severity of the vulnerability and the attacker's goal. For example, some HTTP exploits attacks can result in data theft, Denial of service (DoS) attacks, or even complete web server control.
To illustrate two HTTP attacks, we can look into the most common vulnerabilities: HTTP header and DDoS attacks.
HTTP Host header attack: When a user requests to change the website password for login, the website makes a unique token and sends a password-changing link along with the token via email or message. When the user visits the link, the website checks whether the token is valid. If the token is valid, the user can change the website password. But in this attack, an attacker targets a vulnerable website and user due to HTTP protocol vulnerability. Then, he sends a request on the login page by putting the targeted user's email address for a password reset. Once the HTTP request has been intercepted, the attacker alters the HTTP host header to point to a domain that is under his control. For example,
"POST /password/reset HTTP 1.1
Host: evil-user.net" (portswigger.net)
The website makes a unique token and sends a password-changing link to the user's email address. On the user side, the user gets a genuine email address from the vulnerable website and clicks the link it provides. But as soon as the user clicks on the password-changing link, the attacker receives the genuine token the website sends the user by email in the attacker server. Now the attacker can change the token in the password-changing link, and he can change the user's password.

![Alt Text](Diagram 1.1.png)


