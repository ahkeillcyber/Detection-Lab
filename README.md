# Intrusion Detection and Prevention - Lab 

## Objective

The Detection Lab project aimed to establish a controlled environment for simulating and detecting cyber attacks. The primary focus was to ingest and analyze logs within a Security Information and Event Management (SIEM) system, generating test telemetry to mimic real-world attack scenarios. This hands-on experience was designed to deepen understanding of network security, attack patterns, and defensive strategies.

### Skills Learned

- Advanced understanding of SIEM concepts and practical application.
- Proficiency in analyzing and interpreting network logs.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used

- Security Information and Event Management (SIEM) system for log ingestion and analysis.
- Network analysis tools (such as Wireshark) for capturing and examining network traffic.
- Telemetry generation tools to create realistic network traffic and attack scenarios.
- Linux Terminal

### Environments Used

- VMware Hypervisor - Ubuntu Linux VM
- VMware Hypervisor - Kali Linux VM

### Links

- VMware Hypervisor
- Ubunto Linux ISO File
- Kali Linux ISO File

### Step-By-Step Walkthrough


Step 1 - Install and configure Snort 3 on Ubuntu 20.04

- To begin, start by performing a system update in the Ubuntu VM terminal. 

- Command: sudo apt-get update && sudo apt-get upgrade -y

![Image 1](https://github.com/ahkeillcyber/Detection-Lab/assets/153658518/71f44b57-0c5d-478a-8163-bba91fa4c37b)

- Next, make a directory with the name "snort"

- Command 1: mkdir snort

- Command 2: ls 

![Image 2 1](https://github.com/ahkeillcyber/Detection-Lab/assets/153658518/aad107d4-5da5-408f-98fc-cef0acc56166)

- Now we need to install some prerequisits in order to install Snort 3.

- Command: sudo apt-get install -y build-essential autotools-dev libdumbnet-dev libluajit-5.1-dev libpcap-dev \ zlib1g-dev pkg-config libhwloc-dev cmake liblzma-dev openssl libssl-dev cpputest libsqlite3-dev \ libtool uuid-dev git autoconf bison flex libcmocka-dev libnetfilter-queue-dev libunwind-dev \ libmnl-dev ethtool libjemalloc-dev

![Image 3](https://github.com/ahkeillcyber/Detection-Lab/assets/153658518/b31d062b-0ccd-4e3c-a40d-6503fa57d655)

- Problem 1 - The install did not finish. The error that occured says libtool, zlib1g-dev, libmnl-dev, and libjemalloc-dev are unable to locate package. My first step was to try and download these separately and retry the original command. I ran into the same issue. 

- The solution was I first had to install all the required updates and upgrades using the following commands:

- Command 1: sudo apt-get update

- Command 2: sudo apt-get dist-upgrade

- Command 3: sudo reboot

![Image 4](https://github.com/ahkeillcyber/Detection-Lab/assets/153658518/01b7b34b-1df7-44b4-b874-e569bfc580c7)

Open the command-line interface again and run these commands:
- sudo apt-get install build-essential
- sudo apt-get install -y libpcap-dev libpcre3-dev libdumbnet-dev
- sudo apt-get install -y zliblg-dev liblzma-dev openssl libssl-dev
- sudo apt-get bison flex

![Image 5](https://github.com/ahkeillcyber/Detection-Lab/assets/153658518/06ecd2bd-e135-4f05-8150-7975d7d6825c)

An error displayed after the last command stating that an invalid operation bison was configured. My troubleshooting step here was to research common erros when using the sudo apt-get bison flex when attempting to install snort. 




- To configure and install Snort 3 succesfully on Ubuntu 20.04, it needs to be built from the source. 

- Install Required Built Tools
- There a quite a few build tools and dependencies that need to be installed prior to the build process to ensure a succesful installation of Snort 3. 

- Command: sudo apt install build-essential libpcap-dev libpcre3-dev libnet1-dev zlib1g-dev luajit hwloc libdnet-dev libdumbnet-dev bison flex liblzma-dev openssl libssl-dev pkg-config libhwloc-dev cmake cpputest libsqlite3-dev uuid-dev libcmocka-dev libnetfilter-queue-dev libmnl-dev autotools-dev libluajit-5.1-dev libunwind-dev

