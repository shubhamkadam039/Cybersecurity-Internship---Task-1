# Cyber Security Internship – Task 1

# Task: Scan Your Local Network for Open Ports

# Objective
To learn basic network reconnaissance by discovering open ports on devices on my local network and understanding potential network exposure.

# Steps Followed

1. **Installed Nmap**
    - Downloaded and installed Nmap from its official website.

2. **Found Local IP Range**
    - Used `ipconfig` to determine my local IP address and subnet, e.g., `172.23.195.238/24`.

3. **Scanned Network for Open Ports**
    - Ran the command:
      ```
      nmap -sS 172.23.195.238/24
      ```
4. **Noted IP Addresses and Open Ports**
    - Reviewed the scan results, listing all found devices and their open TCP ports.
PORT     STATE SERVICE
135/tcp  open  msrpc
139/tcp  open  netbios-ssn
445/tcp  open  microsoft-ds
7070/tcp open  realserver

5. **Researched Common Services**
    - Looked up which services typically run on discovered open ports
    - Here’s a short overview of the common services on the ports i found open:

| Port      | Service Name      | Description                                                                |
|-----------|------------------|-----------------------------------------------------------------------------|
| 135/tcp   | msrpc            | Microsoft RPC (Remote Procedure Call). Used for network communication between Windows computers, often for DCOM services and process communication.  |
| 139/tcp   | netbios-ssn      | NetBIOS Session Service. Used for SMB over NetBIOS, older Windows file/printer sharing and network browsing services.                                |
| 445/tcp   | microsoft-ds     | Microsoft Directory Services (SMB over TCP). Modern Windows file and printer sharing (SMB/CIFS) runs here without the need for NetBIOS.              |
| 7070/tcp  | realserver       | RealNetworks RealServer. This port is often used for real-time media streaming applications (audio/video), especially by RealPlayer services.        |

6. **Identified Security Risks**
    - Noted possible security risks for each open port/device, such as exposure to unauthorized access or brute-force attacks.

**Summary of Security Considerations:**
- **135, 139, 445:** These are Windows network ports. They are often targeted by malware and attackers for exploits like ransomware, worms (e.g., WannaCry), and unauthorized file sharing. If not needed, it’s best to block or restrict these ports to minimize exposure.
- **7070:** Media streaming port. If you don't use RealServer or RealPlayer, this port should be closed as it could be abused for unauthorized streaming or as a potential entry point.

7. **Saved Results**
    - Saved the scan output to a file using:
      ```
      nmap -sS 192.168.1.0/24 -oN scan-results.txt
      ```
    - Uploaded this file and any screenshots to this repository.

## Key Findings

- **List of Devices and Open Ports:**
PORT     STATE SERVICE
135/tcp  open  msrpc
139/tcp  open  netbios-ssn
445/tcp  open  microsoft-ds
7070/tcp open  realserver
  
- **Potential Risks:**
    - Open ports can expose devices to attacks if not secured.
    - Unnecessary services should be disabled to minimize exposure.

## What I Learned

- How to use Nmap for scanning my local network.
- How to interpret scan results and identify common network services.
- Awareness of security risks associated with open ports.

## Included Files

- `scan-results.txt` – Nmap scan output
- `scan-results.xml` – Nmap scan output
- `Screenshot 2025-08-04 230810.png` – Screenshot(s) of Nmap output


## Interview Questions & Answers

1. **What is an open port?**  
   A network port that is actively accepting connections from other devices.

2. **How does Nmap perform a TCP SYN scan?**  
   It sends a SYN packet (beginning of a TCP handshake); if it gets a SYN-ACK back, the port is open.

3. **What risks are associated with open ports?**  
   Open ports can be exploited by attackers to gain unauthorized access or exploit vulnerabilities.

4. **Difference between TCP and UDP scanning?**  
   TCP scans look for connection-oriented ports; UDP scans look for connectionless services and are harder to detect.

5. **How can open ports be secured?**  
   By closing unused ports, using firewalls, and securing required services with authentication.

6. **What is a firewall’s role regarding ports?**  
   A firewall filters and controls incoming and outgoing traffic to network ports.

7. **What is a port scan and why do attackers perform it?**  
   A port scan checks which ports are open; attackers use it to find possible targets or exploits.

8. **How does Wireshark complement port scanning?**  
   Wireshark can capture and analyze traffic, giving more visibility into what’s happening during a scan.

## How to Run This Yourself

1. Install [Nmap](https://nmap.org/) on your system.
2. Find your local subnet (e.g., `192.168.1.0/24`).
3. Run:  
   ```
   nmap -sS 
   ```
