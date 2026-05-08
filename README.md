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


# TASK 1
Reconnaissance is the first phase in penetration testing where information is collected about the target system before conducting further security assessments. In this task, several Kali Linux reconnaissance tools were used to gather information from a locally hosted DVWA environment.

Target used in this assessment:

http://localhost/DVWA/login.php
