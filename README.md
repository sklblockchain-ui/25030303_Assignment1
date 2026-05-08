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


# TASK 1
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
