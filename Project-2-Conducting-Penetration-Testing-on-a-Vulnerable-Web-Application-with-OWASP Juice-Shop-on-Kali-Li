### Introduction
This project aims to teach you how to use various tools to conduct penetration testing on a vulnerable web application, specifically OWASP Juice Shop. Designed for educational purposes, OWASP Juice Shop is intentionally insecure, allowing you to explore and understand common web vulnerabilities and learn how to ethically exploit them.

### Prerequisites
- Basic knowledge of web application concepts (HTTP, HTTPS, web servers).
- Familiarity with using the command line interface (CLI).
- An understanding of web development technologies (HTML, JavaScript, etc.).

### Lab Setup and Tools
**Network Diagram**  
Below is a simple network diagram for this lab setup:

```
+------------------+     +------------------+
|    Attacker      |     | Vulnerable App    |
|  Kali Machine    |<--->| (OWASP Juice Shop)|
| (192.168.1.100)  |     |                  |
+------------------+     +------------------+
```

**Tools**
- **Kali Linux**: A Debian-based Linux distribution designed for digital forensics and penetration testing.
- **OWASP Juice Shop**: A vulnerable web application created for educational purposes.
- **Burp Suite**: An integrated platform for conducting security testing on web applications (pre-installed on Kali Linux).

### Installation
**OWASP Juice Shop Setup**  
You can set up OWASP Juice Shop locally using Docker:

1. **Install Docker on Kali Linux**:
   ```bash
   sudo apt-get update
   sudo apt-get install docker.io
   sudo systemctl start docker
   sudo systemctl enable docker
   ```

2. **Pull the OWASP Juice Shop Docker image**:
   ```bash
   sudo docker pull bkimminich/juice-shop
   ```

3. **Run the OWASP Juice Shop container**:
   ```bash
   sudo docker run -d -p 3000:3000 bkimminich/juice-shop
   ```

4. **Access OWASP Juice Shop**: Navigate to `http://localhost:3000` in your web browser.

### Tasks
**Task 1: Identifying Open Ports**
1. **Step 1**: Open a terminal on your Kali Linux machine.
2. **Step 2**: Scan for open ports on the OWASP Juice Shop server using the following command (replace `192.168.1.100` with your instance's IP address):
   ```bash
   nmap 192.168.1.100
   ```
   **Expected Output**: A list of open ports on the server.

**Task 2: SQL Injection**
1. **Step 1**: Launch Burp Suite on your Kali Linux machine.
2. **Step 2**: Configure your browser to use Burp Suite as a proxy (`127.0.0.1:8080`).
3. **Step 3**: Intercept a login request and attempt an SQL injection attack using `' OR '1'='1` as both the username and password.
   **Expected Output**: Successful access to the application using the SQL injection payload.

**Task 3: Cross-Site Scripting (XSS)**
1. **Step 1**: Navigate to a page in OWASP Juice Shop that reflects user input, like the search bar.
2. **Step 2**: Enter an XSS payload, such as `<script>alert('XSS')</script>`.
   **Expected Output**: An alert box appears, confirming the success of the XSS attack.

**Task 4: File Upload Vulnerability**
1. **Step 1**: Go to a file upload page in OWASP Juice Shop (e.g., profile picture upload).
2. **Step 2**: Try to upload a malicious file, such as a PHP reverse shell script.
   **Expected Output**: Determine if the file upload feature is vulnerable by attempting to access or execute the uploaded file.

**Task 5: Directory Traversal**
1. **Step 1**: Use Burp Suite to intercept a request to the server.
2. **Step 2**: Modify the request to include a directory traversal payload, such as `../../../etc/passwd`.
   **Expected Output**: Access to files outside the web root, indicating a directory traversal vulnerability.

**Task 6: Cross-Site Request Forgery (CSRF)**
1. **Step 1**: Create a malicious HTML form that performs an action on behalf of an authenticated user (e.g., changing the user's email).
2. **Step 2**: Load the form in your browser while logged into OWASP Juice Shop.
   **Expected Output**: The action is executed without the user’s consent, demonstrating a CSRF vulnerability.

### Additional Resources
- [OWASP Juice Shop Documentation](https://owasp-juice.shop/)
- [Burp Suite Documentation](https://portswigger.net/burp/documentation)
- [Web Security Academy by PortSwigger](https://portswigger.net/web-security)
- [Kali Linux Documentation](https://www.kali.org/docs/)

This project is designed to help you understand and ethically exploit common web vulnerabilities using Kali Linux and OWASP Juice Shop.
