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

![image](https://github.com/user-attachments/assets/81d832a6-d100-418b-8605-0432ccccbdfb)

4. Implementing LAN Rules:
    - Navigate to Firewall > Rules > LAN in the pfSense WebGUI.
    - Add rules to:
    - Allow HTTP traffic (port 80).
    - Allow DNS traffic (port 53).
    - Allow ICMP (ping) traffic.
    - Allow SSH traffic (port 22).
    - Save and apply the rules.

Ref 2: Complete LAN rules Table

![image](https://github.com/user-attachments/assets/155076f0-2c1a-429d-b82c-1dcbb089586d)

5. Verifying LAN Rules:
    - Use a client machine connected to the LAN to:
    - Perform an nslookup to test DNS resolution.
    - Ping external websites to test ICMP.
    - Access a web page to test HTTP.
    - Use an SSH client to connect to an external SSH server.

Ref 3: Successful ping and nslookup

![image](https://github.com/user-attachments/assets/46c7abab-5058-4723-b3db-410101e2239f)

Ref 4: Access to webpage testing HTTP

![image](https://github.com/user-attachments/assets/db5adffc-7559-4a7a-a5af-3898ac89414b)

Ref 5: Successful SSH connection in WinSCP

![image](https://github.com/user-attachments/assets/f74cb114-8b1f-41d7-b947-55d87a068ce9)

6. Planning WAN Firewall Rules:
    - Document the desired rules for the WAN interface using the PFSENSE-FW-PLANNER spreadsheet.
    - Plan to allow specific traffic types such as HTTP, SFTP, and OpenVPN.

Ref 6: Completed WAN Firewall Rules

![image](https://github.com/user-attachments/assets/d19e9d61-2170-43d9-915a-174cee8bdc8a)

7. Implementing WAN Rules:
    - Navigate to Firewall > Rules > WAN in the pfSense WebGUI.
    - Add rules to:
    - Allow HTTP traffic (port 80).
    - Allow SFTP traffic (port 22).
    - Allow OpenVPN traffic (port 1194).
    - Save and apply the rules.

Ref 7: Completed WAN Rules Table

![image](https://github.com/user-attachments/assets/7c6ef42a-0cb8-4d2c-9c16-6a9c26cc96b8)

8. Verifying WAN Rules:
    - From an external network:
    - Use an SFTP client to connect to the SFTP server through the WAN interface.
    - Access a web page hosted behind the firewall to test HTTP.
    - Establish an OpenVPN connection to test VPN access.
    - Use Zenmap to find active ports and services on target IP address (172.40.0.20)

Ref 8: Successful SFTP Connection 

![image](https://github.com/user-attachments/assets/30a9b48f-cabc-41ce-933e-244061076d70)

Ref 9: Accessing web page hosted behind firewall

![image](https://github.com/user-attachments/assets/796547ab-a756-4d85-a5bb-7cf26f3fd740)

Ref 10: Ports and Services discovered on target host

![image](https://github.com/user-attachments/assets/0c46cffd-0c7d-41a8-9812-c13f5ee0c17f)

9. Independent Challenges:
    - Permit LAN access from the VPN by configuring appropriate rules.
    - Add an ICMP rule using EasyPass to allow pings from specific IP addresses.

Ref 11: OpenVPN rules list in the pfSens WebGUI

![image](https://github.com/user-attachments/assets/b5341286-7756-4394-b664-74462ad8f7c0)

Ref 12: EasyRule for ICMP in the Firewall Rules WAN Table

![image](https://github.com/user-attachments/assets/ca045289-3121-45bb-8346-eea480dbf4f9)

10. Monitoring and Logging:
    - Enable logging for specific firewall rules to monitor traffic.
    - Navigate to Status > System Logs > Firewall to view logged entries and verify rule effectiveness.

Ref 13: Attempted ICMP requests in firewall log

![image](https://github.com/user-attachments/assets/265dd2e5-d7bc-4c5e-bcbf-a9cad16117cd)

### Key Takeaways
This lab emphasized how properly configuring a firewall is esential when it comes to maintaining effective network security. By configuring and verifying bot LAN and WAN rules using the pfSense web UI, I learned how to manage and control network traffic effectively. Utilizing pfSense provided me with hands-on experience managing firewall policies and access controls. This lab provided me with practical skills in firewall management which is essential for securing any network.
