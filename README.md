# Detection-Lab

## Objective
[Brief Objective - Remove this afterwards]

The Detection Lab project aimed to establish a controlled environment for simulating and detecting cyber attacks. The primary focus was to ingest and analyze logs within a Security Information and Event Management (SIEM) system, generating test telemetry to mimic real-world attack scenarios. This hands-on experience was designed to deepen understanding of network security, attack patterns, and defensive strategies.

### Skills Learned
[Bullet Points - Remove this afterwards]

- Advanced understanding of SIEM concepts and practical application.
- Proficiency in analyzing and interpreting network logs.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used
[Bullet Points - Remove this afterwards]

- Security Information and Event Management (SIEM) system for log ingestion and analysis.
- Network analysis tools (such as Wireshark) for capturing and examining network traffic.
- Telemetry generation tools to create realistic network traffic and attack scenarios.

## Steps
drag & drop screenshots here or use imgur and reference them using imgsrc

Every screenshot should have some text explaining what the screenshot is about.

## Install and configure Snort 3 on Ubuntu 20.04.
To begin, start by performing a system update. 

sudo apt-get update && sudo apt-get upgrade -y
Insert Image 1

Next, make a directory with the name "snort"

mkdir snort
ls 
Insert Image 2.1

Now we need to install some prerequisits in order to stall Snort 3.

sudo apt-get install -y build-essential autotools-dev libdumbnet-dev libluajit-5.1-dev libpcap-dev \ zlib1g-dev pkg-config libhwloc-dev cmake liblzma-dev openssl libssl-dev cpputest libsqlite3-dev \ libtool uuid-dev git autoconf bison flex libcmocka-dev libnetfilter-queue-dev libunwind-dev \ libmnl-dev ethtool libjemalloc-dev

The install did not finish. The error that occured says libtool, zlib1g-dev, libmnl-dev, and libjemalloc-dev are unable to locate package. My firset step was to try and download these separately and retry the original command. I ran into the same issue. 

Insert Image 3

The solution was I firset had to install all the required pre-requisites.

sudo apt-get update
sudo apt-get dist-upgrade
sudo reboot

Insert Image 4


To configure and install Snort 3 succesfully on Ubuntu 20.04, it needs to be built from the source. 

## Install Required Built Tools
There a quite a few build tools and dependencies that need to be installed prior to the build process to ensure a succesful installation of Snort 3. 

sudo apt install build-essential libpcap-dev libpcre3-dev libnet1-dev zlib1g-dev luajit hwloc libdnet-dev libdumbnet-dev bison flex liblzma-dev openssl libssl-dev pkg-config libhwloc-dev cmake cpputest libsqlite3-dev uuid-dev libcmocka-dev libnetfilter-queue-dev libmnl-dev autotools-dev libluajit-5.1-dev libunwind-dev

