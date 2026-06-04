🛡️ Task 4: Setup and Use a Firewall on Windows

Author:-Aashish  
Program:- BCA, Cyber Security  
Organization:-Elevate Labs Cybersecurity Internship  

---

## 🎯 Objective
To configure and test basic firewall rules to actively allow or block network traffic, demonstrating a practical understanding of network traffic filtering.

## 🛠️ Tools & Technologies Used
OS: Windows
Firewall Tool: Windows Defender Firewall with Advanced Security (`wf.msc`)[cite: 1]
Testing Tool: Windows PowerShell
Key Concepts: Inbound/Outbound Rules, Port Management, TCP/IP Protocols[cite: 1].

---

⚙️ Steps Executed & Documentation

1. Blocking Inbound Traffic (Port 23 - Telnet)
Action: Opened Windows Firewall configuration (`wf.msc`)[cite: 1].
Rule Creation: Created a new **Inbound Rule** specific to a Port[cite: 1].
Protocol & Port: Selected `TCP` and specified local port `23` (Telnet)[cite: 1].
Security Action: Selected **Block the connection** to restrict unencrypted Telnet traffic across Domain, Private, and Public profiles[cite: 1].

Here: Showing the Blocked Rule with the Red Icon)

<img width="1920" height="1080" alt="Screenshot (15)" src="https://github.com/user-attachments/assets/73836834-a678-4a30-80f8-cb4b192ee1e3" />


2. Testing the Firewall Rule
Action: Used PowerShell to verify the firewall's effectiveness locally[cite: 1].
Command Executed: `Test-NetConnection -ComputerName 127.0.0.1 -Port 23`
Result: The connection failed (`TcpTestSucceeded : False`), confirming the firewall successfully blocked the inbound traffic on Port 23[cite: 1].

Here: Showing the PowerShell test result)

<img width="1920" height="1080" alt="Screenshot (17)" src="https://github.com/user-attachments/assets/bf1cf228-a844-4c50-aa41-8d1ab8bbe330" />


3. Allowing Inbound Traffic (Port 22 - SSH)
Action: Created an additional Inbound Rule to handle secure connections[cite: 1].
Protocol & Port: Selected `TCP` and specified local port `22` (SSH)[cite: 1].
Security Action: Selected **Allow the connection** to permit incoming SSH traffic[cite: 1].

(Insert Screenshot 3 Here: Showing the Allowed Rule with the Green Icon)

<img width="1920" height="1080" alt="Screenshot (18)" src="https://github.com/user-attachments/assets/e6a39626-155c-4532-9f68-e5a4c47c1a83" />


4. System Restoration
Action: Deleted all custom test rules (Blocked Port 23 & Allowed Port 22) from the Inbound Rules list to restore the Windows Firewall to its original, secure baseline state[cite: 1].

---

📝 Summary: How a Firewall Filters Traffic
A firewall acts as a critical security gateway for a system or network. It filters incoming (inbound) and outgoing (outbound) traffic by inspecting data packets and evaluating them against a predefined set of security rules[cite: 1]. 

When a packet attempts to enter the network, the firewall checks its origin, destination, protocol, and port numbers. If the packet matches an 'Allow' rule (like secure SSH traffic on Port 22), it is permitted through. If it matches a 'Block' rule (like insecure Telnet traffic on Port 23), the packet is instantly dropped[cite: 1]. This mechanism prevents unauthorized access and mitigates the risk of external cyber threats.

