# Configuring-Custom-Firewall-Rules-with-pfSense

## Objective

The objective of this project was to configure custom firewall rules using pfSense to manage and secure network traffic effectively. The focus was on implementing strict access controls to enhance network security by allowing only specific types of traffic through the firewall.

### Skills Learned

- Understanding firewall concepts and different configurations settings.
- Creating and managing custom firewall rules.
- Enhanced knowledge of network segmentation and traffic control.
- Development of security policies to control access.
- Practical experience with pfSense firewall-router.

### Tools Used

- pfSense
- Wireshark
- OpenVPN
- WinSCP
- FileZilla
- Nmap

## Steps
1. Download and Install pfSense:
    - Download the pfSense ISO image from the official website.
    - Use a tool like Rufus to create a bootable USB drive.
    - Boot the target hardware from the USB drive and follow the installation wizard to install pfSense.

2. Initial Configuration:
    - Connect to the pfSense WebGUI via a web browser using the default LAN IP address.
    - Set up the initial configuration, including hostname, domain, DNS servers, and the admin password.
    - Configure the WAN and LAN interfaces with appropriate IP settings.

3. Planning LAN Firewall Rules:
    - Document the desired rules for the LAN interface using the PFSENSE-FW-PLANNER spreadsheet.
    - Plan to allow specific traffic types such as HTTP, DNS, ICMP, and SSH.

Ref 1: PFSENSE-FW-PLANNER spreadsheet

![image](https://github.com/user-attachments/assets/cd6cb1be-f8d2-4e62-ae3b-4b01eed22655)

4. Implementing LAN Rules:
    - Navigate to Firewall > Rules > LAN in the pfSense WebGUI.
    - Add rules to:
    - Allow HTTP traffic (port 80).
    - Allow DNS traffic (port 53).
    - Allow ICMP (ping) traffic.
    - Allow SSH traffic (port 22).
    - Save and apply the rules.

Ref 2: Complete LAN rules Table

![image](https://github.com/user-attachments/assets/23673826-acaf-42ea-8bee-6b5b8b2c8099)

5. Verifying LAN Rules:
    - Use a client machine connected to the LAN to:
    - Perform an nslookup to test DNS resolution.
    - Ping external websites to test ICMP.
    - Access a web page to test HTTP.
    - Use an SSH client to connect to an external SSH server.

Ref 3: Successful ping and nslookup

![image](https://github.com/user-attachments/assets/c6f28d17-1acc-4672-ab55-ed15dd311eec)

Ref 4: Successful SSH connection in WinSCP

![image](https://github.com/user-attachments/assets/8cecd4d6-fb55-4ce0-9afa-8b57e14ad322)

6. Planning WAN Firewall Rules:
    - Document the desired rules for the WAN interface using the PFSENSE-FW-PLANNER spreadsheet.
    - Plan to allow specific traffic types such as HTTP, SFTP, and OpenVPN.

Ref 5: Completed WAN Firewall Rules

![image](https://github.com/user-attachments/assets/57cc9b19-7be6-4948-a0c8-af9039b134fc)

7. Implementing WAN Rules:
    - Navigate to Firewall > Rules > WAN in the pfSense WebGUI.
    - Add rules to:
    - Allow HTTP traffic (port 80).
    - Allow SFTP traffic (port 22).
    - Allow OpenVPN traffic (port 1194).
    - Save and apply the rules.

Ref 6: Completed WAN Rules Table

![image](https://github.com/user-attachments/assets/1d681184-e5c3-4777-9a7b-017ef4b4b9a1)

8. Verifying WAN Rules:
    - From an external network:
    - Use an SFTP client to connect to the SFTP server through the WAN interface.
    - Access a web page hosted behind the firewall to test HTTP.
    - Establish an OpenVPN connection to test VPN access.

Ref 7: Successful SFTP Connection 

![image](https://github.com/user-attachments/assets/d131eb22-91d1-429b-ab58-4d96976fd590)

Ref 8: Accessing web page hosted behind firewall

![image](https://github.com/user-attachments/assets/585e05a6-3751-44ff-9080-9285f3236bab)

9. Independent Challenges:
    - Permit LAN access from the VPN by configuring appropriate rules.
    - Add an ICMP rule using EasyPass to allow pings from specific IP addresses.

Ref 9: OpenVPN rules list in the pfSens WebGUI

![image](https://github.com/user-attachments/assets/99b85b7f-d353-456a-8d4b-eac80abab969)

Ref 10: EasyRule for ICMP in the Firewall Rules WAN Table

![image](https://github.com/user-attachments/assets/32cb71ed-791a-4d26-b451-08487b5b2697)

10. Monitoring and Logging:
    - Enable logging for specific firewall rules to monitor traffic.
    - Navigate to Status > System Logs > Firewall to view logged entries and verify rule effectiveness.

Ref 11: Attempted ICMP requests in firewall log

![image](https://github.com/user-attachments/assets/467b87ff-2a98-46cb-b394-2ed9aac67d49)

### Key Takeaways
This lab emphasized how properly configuring a firewall is esential when it comes to maintaining effective network security. By configuring and verifying bot LAN and WAN rules using the pfSense web UI, I learned how to manage and control network traffic effectively. Utilizing pfSense provided me with hands-on experience managing firewall policies and access controls. This lab provided me with practical skills in firewall management which is essential for securing any network.
