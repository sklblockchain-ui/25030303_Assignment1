# TMS6064 Cyber Security Assignment 1
- **Name:** ZAEIM HUZAIRY  
- **Matric Number:** 25030303  
- **Course:** TMS6064 Cyber Security 

## Disclaimer
This project is conducted strictly for educational purposes only in a controlled lab environment using authorized targets.

## Setting up before starting lab

Before starting the penetration testing tasks, the DVWA (Damn Vulnerable Web Application) environment was prepared and configured in a local lab setup. This preparation ensures that all required services, applications, and configurations are functioning correctly before conducting reconnaissance and security testing activities. The setup process also provides a safe and controlled environment for learning ethical hacking and penetration testing techniques.

### Installing DVWA
This step installs the DVWA application and its required dependencies in the Linux environment.

![Installing DVWA](install-dvwa.png)

### Cloning DVWA
The DVWA source files were cloned from the official GitHub repository into the web server directory.

![Cloning DVWA](cloning-DVWA.png)

### Configuring DVWA
The configuration file was modified to connect DVWA with the local database and enable the application to run properly.

![Config DVWA](config-DVWA.png)

### Apache Status
The Apache web server service was checked to ensure the DVWA website could be accessed through the browser.

![Apache Status](apache-status.png)

### Target IP
The target IP address and localhost environment were verified before starting reconnaissance activities.

![Target IP](iptarget.png)

### DVWA Localhost Access
After completing the installation and configuration process, the DVWA login page was successfully accessed through the localhost environment using a web browser. This confirms that the Apache web server, PHP, and database services are functioning correctly and the DVWA application is ready for penetration testing activities.

![DVWA Localhost](DVWAlocalhost.png)


# TASK 1 - Reconnaissance
Reconnaissance is the first phase in penetration testing where information is collected about the target system before conducting further security assessments. In this task, several Kali Linux reconnaissance tools were used to gather information from a locally hosted DVWA environment.

Target used in this assessment:

http://localhost/DVWA/login.php

---

## Tool 1 — Nmap

Nmap is a network scanning tool used during the reconnaissance phase in penetration testing. It helps identify open ports, running services, and operating system information on the target machine. In this task, Nmap was used to scan the locally hosted DVWA web application running on localhost.

### Installing Nmap
This step installs the Nmap tool in Kali Linux before starting the reconnaissance and scanning activities. The tool is required to perform network discovery and gather target information during penetration testing.

![Nmap Installation](nmap-1Install.png)

### Service Version Detection
This test is conducted to identify the versions of services running on the target machine such as Apache or HTTP services. Identifying service versions helps penetration testers understand what applications are running and whether they may contain vulnerabilities.

```bash
nmap -sV localhost
```

![Nmap Version Detection](nmap-2VersionDetection.png)

### Operating System Detection
This test is conducted to identify the operating system used by the target machine. Knowing the operating system helps penetration testers plan suitable testing methods and understand the target environment better.

```bash
sudo nmap -O localhost
```

![Nmap OS Detection](nmap-3OSDetection.png)

### Aggressive Scan
This test is conducted to perform more advanced reconnaissance activities including operating system detection, service version detection, script scanning, and traceroute. It helps gather more detailed information about the target before moving to the next penetration testing phase.

```bash
sudo nmap -A localhost
```

![Nmap Aggressive Scan](nmap-4AggresiveScan.png)

### Conclusion
Nmap successfully gathered useful information about the localhost target environment. The tool is important during the reconnaissance phase because it helps penetration testers understand the target system before conducting further security assessments.

---
## Tool 2 — Hping3

Hping3 is a network packet analysis and packet crafting tool commonly used during penetration testing and reconnaissance activities. It helps penetration testers analyze network responses, test connectivity, and understand how the target machine responds to different packet requests.

### Installing Hping3
This step installs the Hping3 tool in Kali Linux before starting packet testing and network analysis activities.

![Hping3 Installation](hping3-1Install.png)

### Basic Packet Test
This test is conducted to verify communication between the testing machine and the target system. It helps confirm that the target is reachable and responding to packet requests.

```bash
sudo hping3 localhost
```

![Hping3 Basic Test](hping3-2BasicTest.png)

### SYN Packet Test
This test is conducted to send SYN packets to port 80 on the target machine. The purpose of this test is to analyze how the target responds to connection requests and identify active services such as web servers.

```bash
sudo hping3 -S localhost -p 80
```

![Hping3 SYN Packet](hping3-3SYNPacket.png)

### ICMP Packet Test
This test is conducted to verify whether the target machine responds to ICMP requests. It helps test network connectivity and response behavior between systems.

```bash
sudo hping3 --icmp localhost
```

![Hping3 ICMP Test](hping3-4icmp.png)

### Conclusion
Hping3 successfully tested network communication and packet responses from the localhost target. The tool is useful during penetration testing because it helps analyze how the target system handles different network packet requests.

---
## Tool 3 — DNSRecon

DNSRecon is a DNS enumeration tool used during the reconnaissance phase in penetration testing. It helps gather DNS-related information from the target system such as domain records, nameserver information, and DNS configurations. This information helps penetration testers understand the target environment before conducting further security testing.

### Installing DNSRecon
This step installs the DNSRecon tool in Kali Linux before starting DNS enumeration and reconnaissance activities.

![DNSRecon Installation](dnsrecon-1.png)

### General DNS Enumeration
This test is conducted to gather general DNS-related information from the target domain. The purpose of this test is to identify available DNS records and understand the DNS configuration used by the target environment.

```bash
dnsrecon -d localhost
```

![DNSRecon General Enumeration](dnsrecon-2basictest.png)

### Standard DNS Enumeration
This test is conducted to perform standard DNS enumeration against the target domain. The command helps identify DNS-related configurations and verify available DNS services used by the target machine.

```bash
dnsrecon -d localhost -t std
```

![DNSRecon Standard Enumeration](dnsrecon-3.png)

### Conclusion
DNSRecon successfully performed DNS reconnaissance activities against the localhost target. The tool is useful during penetration testing because it helps collect DNS information and improves understanding of the target environment before conducting further assessments.

---
## Tool 4 — Recon-ng

Recon-ng is a web reconnaissance framework used during penetration testing to automate information gathering and reconnaissance activities. The framework helps penetration testers organize reconnaissance tasks, manage workspaces, and use different modules for collecting target information efficiently.

### Installing Recon-ng
This step installs the Recon-ng framework in Kali Linux before starting reconnaissance and information gathering activities.

![Recon-ng Installation](reconng-1install.png)

### Starting Recon-ng Framework
This step is conducted to launch the Recon-ng framework environment before using its reconnaissance modules and workspace management features.

```bash
recon-ng
```

![Recon-ng Framework](reconng-2.png)

### Marketplace Search
This command is used to search available reconnaissance modules inside the Recon-ng framework. The purpose of this step is to identify useful modules that can be used for information gathering and reconnaissance activities.

```bash
marketplace search
```

![Recon-ng Marketplace Search](reconng-3marketplacesearch.png)

### Workspace Management
This command is used to display existing workspaces and create a dedicated workspace for the target assessment. Workspaces help organize reconnaissance activities and separate project data properly.

```bash
workspaces list
workspaces create dvwa
```

![Recon-ng Workspaces](reconng-4workspaces.png)

### Conclusion
Recon-ng successfully provided a structured framework for managing reconnaissance activities and organizing information gathering tasks. The framework is useful during penetration testing because it helps automate reconnaissance processes and improve workflow management.


---
# Task 2 — Maintaining Access
Maintaining access is a phase in penetration testing where a tester learns how access to a system can still be available after entering the target system. In this task, several tools in Kali Linux were explored to understand how they work in a controlled lab environment.

For this activity, DVWA (Damn Vulnerable Web Application) was used as the practice target because it is designed for cybersecurity learning and testing.

## DVWA Lab Environment Setup

![DVWA Login](images/dvwa-login.png)

## Disclaimer
This project is for educational purposes only. All testing was done in a safe lab environment using Kali Linux and DVWA on localhost. No real websites, servers, or public systems were involved in this activity. The Damn Vulnerable Web Application (DVWA) was successfully deployed on Kali Linux using a localhost environment. DVWA was used as the authorized testing platform for cybersecurity laboratory activities and penetration testing simulations.


---

# Tool 1 — Webshells

Webshells are files that can be uploaded to a vulnerable website to allow remote access through a web browser. Kali Linux already provides several example webshell files for learning purposes.

---

## Accessing the Webshell Folder

This step was done to check the available webshell categories provided in Kali Linux.

```bash
cd /usr/share/webshells
ls
```

![Webshells Folder](webshells-1folder.png)

### Description
The command was used to open the webshell directory in Kali Linux and list the available folders. Different folders are provided for different web programming languages such as PHP, ASP, JSP, and Perl.

---

## Viewing PHP Webshell Files

This step focused on PHP webshell examples because DVWA uses PHP.

```bash
cd php
ls
```

![PHP Webshells](webshells-2phpfolder.png)

### Description
The command was used to enter the PHP folder and display the available PHP webshell files. These files are commonly used in web security testing and learning activities inside a safe lab environment.

---

# Tool 2 — Weevely

Weevely is a tool used to create a PHP shell file. It helps testers understand how remote access through a website may happen during penetration testing practice.

---

## Checking Weevely Tool

This step was done to check whether Weevely was already installed and working in Kali Linux.

```bash
weevely
```

![Weevely Information](weevely-1.png)

### Description
The command was used to display the Weevely information and available options. It also shows how the tool is used for creating and managing PHP shell files.

---

## Creating a PHP Payload

This step created a sample PHP file named `test.php` for learning purposes.

```bash
weevely generate password test.php
```

![Weevely Payload](weevely-2.png)

### Description
The command was used to generate a sample PHP payload file called `test.php`. This file can later be used in a controlled DVWA upload activity to understand how maintaining access works in web applications.

---

# Tool 3 — Cryptcat

Cryptcat is a networking tool that allows communication between systems. It is similar to Netcat but supports encrypted communication.

---

## Installing and Viewing Cryptcat Options

This step was done to install Cryptcat and view the available commands and options.

```bash
sudo apt install cryptcat -y
cryptcat -h
```

![Cryptcat](cryptcat-1.png)

### Description
The command was used to install Cryptcat and display its help menu. This helps users understand the available networking and communication features provided by the tool.

---

# Comparison of Tools

| Tool | Main Use | Function in Lab |
|------|------|------|
| Webshells | Collection of shell files | Learning about web-based access |
| Weevely | PHP shell generator | Creating PHP payload files |
| Cryptcat | Communication tool | Understanding encrypted connections |

---

# Conclusion

In this task, several maintaining access tools available in Kali Linux were explored inside a controlled DVWA lab environment. The activity helped improve understanding of how webshells, payload generation, and communication tools are used during cybersecurity testing.

Webshells help testers understand web-based access methods, Weevely helps create PHP shell files for learning purposes, and Cryptcat helps demonstrate communication between systems. Overall, this task provided practical exposure to maintaining access concepts in penetration testing while following safe and ethical cybersecurity practices.

