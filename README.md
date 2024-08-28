# Ethical Hacking for Beginners

## Project 1: Enumerating and Scanning a Local Network with Nmap on Kali Linux

### Overview
This project is focused on learning the basics of network enumeration and scanning using Nmap, a powerful network scanning tool, on Kali Linux. I will  explore how to identify hosts, services, and potential vulnerabilities within a local network.
Pre-requisites
Basic understanding of networking concepts (IP addresses, ports, etc.).
Familiarity with using the command line interface (CLI).
Kali Linux installed on your machine (either natively, on a virtual machine, or as a live boot).
Lab Set-up and Tools
Tools
Kali Linux: A Debian-derived Linux distribution designed for digital forensics and penetration testing.
Nmap: Network exploration tool and security/port scanner (pre-installed on Kali Linux).
A local network with multiple devices connected (computers, printers, IoT devices, etc.).

### Steps to Follow

#### Step 1: Setting Up Your Environment
- **Install Kali Linux**: Ensure that you have Kali Linux installed on your machine, either directly or via a virtual machine.
- **Update Kali Linux**: Before starting, update your system with the following commands:

  
  sudo apt update && sudo apt upgrade -y

 expected image 
 <img width="941" alt="image" src="https://github.com/user-attachments/assets/ed9b035d-cbf8-47d7-8edd-48f4e46ea1ef">

  

#### Step 2: Understanding Nmap
- **Nmap (Network Mapper)**: Nmap is used for network discovery and security auditing. It helps you create a map of the network by identifying hosts and services.
  n/b Open a terminal on your Kali Linux machine. Run a basic scan on your local network.
  Replace 192.168.1.1/24 with your network's IP range.

#### Step 3: Basic Nmap Commands
1. **Scan a Single IP Address**:
   
   nmap <IP-Address>
   
   Example:
   

   nmap 192.168.1.1
   Expected Output: A list of devices on your network, their IP addresses, and the open ports.

<img width="613" alt="image" src="https://github.com/user-attachments/assets/68a2d831-c7fb-4ffa-9a70-1cd116e0af11">

   
3. **Scan a Range of IP Addresses**:
     
   nmap 192.168.1.1-254
   
   expected output:
   range of IP Addresses

<img width="896" alt="image" src="https://github.com/user-attachments/assets/8705eadd-f519-4a5f-969c-35398e5f027c">

   
  
4. **Scan an Entire Subnet**:
   
   
 nmap 192.168.1.0/24

Expected Output: A list of devices on your network, their IP addresses, and the open ports.

 <img width="547" alt="image" src="https://github.com/user-attachments/assets/08482d88-5ee6-4476-859a-d92906e0f3a5">

   
5. **Detailed Output**:
   
   
nmap -v 192.168.1.1
   expected output results from my IP address.

<img width="425" alt="image" src="https://github.com/user-attachments/assets/90752501-4072-49f3-87d5-bef495da7d22">


#### Step 4: Advanced Nmap Scanning Techniques
1. **Service Version Detection**:
   nmap -sV 192.168.1.1
   
   expected output:Expected Output: A detailed list of open ports and the services running on them, including version information.

<img width="954" alt="image" src="https://github.com/user-attachments/assets/4a202f81-996a-4421-a0b8-c07cae72eccd">

   
3. **Operating System Detection**:
 Use the -O option to detect the operating systems of devices on the network:


sudo nmap -O 192.168.1.1/24
Expected Output: The operating system details of the devices on the network

   sudo nmap -O 192.168.1.1/24

<img width="554" alt="image" src="https://github.com/user-attachments/assets/58296772-f33e-4f5b-bd5c-41c79832bccc">

   
5. **Aggressive Scan**:
   
sudo nmap -A 192.168.1.1/24

   Perform an aggressive scan using the -A option, which includes OS detection, version detection, script scanning, and traceroute:

<img width="954" alt="image" src="https://github.com/user-attachments/assets/b804bc94-51f3-4423-ae41-fc2df6f4056e">


   
   
7. **Vulnerability Scanning**:

   
   nmap --script vuln 192.168.1.1
   expected output:
 
   <img width="421" alt="image" src="https://github.com/user-attachments/assets/7bf357b3-62ab-4b17-bdf0-2cf70a29dceb">


#### Step 5: Documenting Your Findings
 **Save Output to a File**:
 ```bash
 
  nmap -oN scan_results.txt 192.168.1.1
  
**Create a Report**: Document your findings, including IP addresses, open ports, services, and any detected vulnerabilities.


### Conclusion
This project serves as an introduction to ethical hacking by teaching you how to use Nmap for network enumeration and scanning. As you progress, you'll gain more advanced skills in ethical hacking and cybersecurity.

Additional Resources
Nmap Official Documentation Nmap Cheat Sheet Online Nmap Course on Udemy

This project will give you a solid foundation in using Nmap for network scanning and enumeration, essential skills for any ethical hacker.
bash
Copy code
nmap -sV 192.168.1.1

