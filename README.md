# Cybersecurity-Internship---Task-1
Task: Scan Your Local Network for Open Ports
Objective
To learn basic network reconnaissance by discovering open ports on devices on my local network and understanding potential network exposure.

Steps Followed
Installed Nmap

Downloaded and installed Nmap from its official website.

Found Local IP Range

Used ipconfig (on Windows) or ifconfig/ip a (on Linux/Mac) to determine my local IP address and subnet, e.g., 192.168.1.0/24.

Scanned Network for Open Ports

Ran the command:

text
nmap -sS 192.168.1.0/24
(Adjusted the IP range to match my network.)

Noted IP Addresses and Open Ports

Reviewed the scan results, listing all found devices and their open TCP ports.

(Optional) Used Wireshark

Optionally captured network packets with Wireshark during the scan and analyzed the results for deeper understanding.

Researched Common Services

Looked up which services typically run on discovered open ports (e.g., port 22 = SSH, port 80 = HTTP).

Identified Security Risks

Noted possible security risks for each open port/device, such as exposure to unauthorized access or brute-force attacks.

Saved Results

Saved the scan output to a file using:

text
nmap -sS 192.168.1.0/24 -oN scan-results.txt
Uploaded this file (and any screenshots/pcap from Wireshark) to this repository.

Key Findings
List of Devices and Open Ports:

(You can fill this in; example:)

192.168.1.5: 22/tcp (SSH)

192.168.1.10: 80/tcp (HTTP), 443/tcp (HTTPS)

Potential Risks:

Open ports can expose devices to attacks if not secured.

Unnecessary services should be disabled to minimize exposure.

What I Learned
How to use Nmap for scanning my local network.

How to interpret scan results and identify common network services.

Awareness of security risks associated with open ports.

Included Files
scan-results.txt – Nmap scan output

screenshot.png – (Optional) Screenshot(s) of Nmap/Wireshark output

(Any additional files, e.g., wireshark-capture.pcap)

Interview Questions & Answers
What is an open port?
A network port that is actively accepting connections from other devices.

How does Nmap perform a TCP SYN scan?
It sends a SYN packet (beginning of a TCP handshake); if it gets a SYN-ACK back, the port is open.

What risks are associated with open ports?
Open ports can be exploited by attackers to gain unauthorized access or exploit vulnerabilities.

Difference between TCP and UDP scanning?
TCP scans look for connection-oriented ports; UDP scans look for connectionless services and are harder to detect.

How can open ports be secured?
By closing unused ports, using firewalls, and securing required services with authentication.

What is a firewall’s role regarding ports?
A firewall filters and controls incoming and outgoing traffic to network ports.

What is a port scan and why do attackers perform it?
A port scan checks which ports are open; attackers use it to find possible targets or exploits.

How does Wireshark complement port scanning?
Wireshark can capture and analyze traffic, giving more visibility into what’s happening during a scan.
