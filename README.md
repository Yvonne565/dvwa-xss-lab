# dvwa-xss-lab
This repository contains the documentation, screenshots, and steps for a lab on Reflected Cross-Site Scripting (XSS) using DVWA on Kali Linux with Apache. The lab illustrates how unsanitized user input can lead to JavaScript execution in browsers.
CROSS-SITE SCRIPTING (XSS) LAB

ETHICAL NOTICE
This lab was conducted in a controlled lab environment using an intentionally vulnerable web application strictly for educational purposes.


LAB OBJECTIVE

The objective of this lab is to demonstrate a Cross-Site Scripting (XSS) vulnerability by injecting malicious JavaScript into a web application that does not properly validate or sanitize user input.


TOOLS USED

- Kali Linux
- Web Browser (Firefox)
- Intentionally vulnerable web application (DVWA)
- Local web server (Apache)


LAB ENVIRONMENT

Operating System: Kali Linux  
Target Application: Damn Vulnerable Web Application (DVWA)  
Vulnerability Type: Reflected Cross-Site Scripting (XSS)  


STEP-BY-STEP PROCEDURE

STEP 1: START KALI LINUX
Launch the Kali Linux virtual machine and log in.

STEP 2: START APACHE WEB SERVER
Open the terminal and start the Apache server:

sudo service apache2 start

STEP 3: ACCESS DVWA
Open Firefox and navigate to:

http://127.0.0.1/dvwa

Log in using:
Username: admin  
Password: password

STEP 4: SET DVWA SECURITY LEVEL
Navigate to DVWA Security settings and set the security level to "Low", then save.

STEP 5: NAVIGATE TO XSS (REFLECTED)
From the DVWA menu, select:
XSS (Reflected)

STEP 6: TEST USER INPUT
Enter a normal input such as:

Hello

Observe that the input is reflected on the page.

STEP 7: INJECT XSS PAYLOAD
Enter the following payload into the input field:

<script>alert('XSS')</script>

STEP 8: OBSERVE RESULT
An alert pop-up appears in the browser, confirming successful execution of injected JavaScript.

9. Summary Output Statement
After injecting the XSS payload, a JavaScript alert pop-up appeared, confirming successful execution of malicious code. This demonstrates the presence of a reflected Cross-Site Scripting (XSS) vulnerability due to improper input validation.  



KEY PAYLOADS USED

<script>alert('XSS')</script>


FINDINGS AND OBSERVATIONS

The application failed to properly validate and sanitize user input, allowing JavaScript code to be executed in the browser. This confirms the presence of a reflected XSS vulnerability. An attacker could exploit this vulnerability to steal session cookies, perform phishing attacks, or manipulate webpage content.


CONCLUSION

Cross-Site Scripting (XSS) is a serious web application vulnerability that occurs when user input is not properly sanitized. This lab demonstrated how easily an attacker can inject malicious scripts into a vulnerable application. Implementing input validation, output encoding, and secure coding practices is essential to prevent XSS attacks.



