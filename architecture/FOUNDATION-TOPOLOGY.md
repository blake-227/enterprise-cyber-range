\# Foundation Network Architecture



```mermaid

flowchart TD



&#x20;   HOST\["Windows 11 Host<br/>10.10.10.1"]



&#x20;   NETWORK\["VMnet2<br/>10.10.10.0/24<br/>Host-Only Cyber Range"]



&#x20;   KALI\["KP-SOC01<br/>Kali Purple<br/>10.10.10.10<br/>SOC / Blue Team"]



&#x20;   WINDOWS\["WIN11-USER01<br/>Windows 11<br/>10.10.10.20<br/>Employee Workstation"]



&#x20;   UBUNTU\["UBUNTU-SRV01<br/>Ubuntu Server<br/>10.10.10.30<br/>Linux Server"]



&#x20;   HOST --> NETWORK



&#x20;   NETWORK --> KALI

&#x20;   NETWORK --> WINDOWS

&#x20;   NETWORK --> UBUNTU

```



\## Current Environment



The Project 1 environment is completely isolated from the Internet.



All cyber range systems communicate through VMware VMnet2.



Future versions of this topology will introduce pfSense, additional network segments, Active Directory, cloud infrastructure, centralized monitoring, and a dedicated attack environment.

