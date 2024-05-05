# Small Network Lab
![image](https://github.com/WesleyKProfile/Small-Network-Lab/assets/168662972/e0211389-86db-4280-9737-45cc6d883690)
<sub>*ref 1. final network topology *<\sub>

## Objective
The Small Network Lab aimed to construct a simulated network environment using Cisco Packet Tracer, integrating subnetting and VLANs to enhance network segmentation. The primary focus was to design and implement subnetting schemes to optimize IP address allocation and VLAN configurations, and to logically segregate network traffic. This hands-on experience provided practical insights into network segmentation, IP addressing, and VLAN deployment, fostering a deeper understanding of network security principles and defensive strategies.

### Skills Learned

- Fluency in network design.
- Mastery of subnetting techniques for efficient IP address allocation.
- Strategic deployment of VLANs to improve network scalability and management.
- Proficiency in ensuring seamless operation of network devices and services.

## Steps
1. Determined the hardware requirements for the project, excluding servers and cabling.
![image](https://github.com/WesleyKProfile/Small-Network-Lab/assets/168662972/5c40454e-8637-4341-8f60-a779f66dffd2)
<sub>*ref 2. all hardware, excluding servers and cabling*<\sub>

2. Established wired connections for all devices and organized them into VLAN groups for network segmentation and management.
![image](https://github.com/WesleyKProfile/Small-Network-Lab/assets/168662972/4f5e2a1a-b0f7-4139-819a-2609ed11b0a5)
<sub>*ref 3. colored circles show VLANs to be implemented*<\sub>

3. Performed subnetting calculations.
- Selected 192.169.1.0 for the base network IP address
- Determined the number of subnets required for the network by solving the equation 2^n = 4, where 'n' represents the number of subnet bits. Through this calculation, it was determined that 'n' equals 2, indicating the need for four subnets.
- As the network is using a Class C private IP address range, it's established that the subnet mask is 255.255.255.0.
- Converting the subnet mask to binary format and applying the two subnet bits determined from the previous equation, we obtain: 11111111.11111111.11111111.11000000.
- The new subnet mask, expressed in decimal notation, is 255.255.255.192.
- The value '192' in the last octet of the new subnet mask indicates that the block size is 64.
- With all necessary information at hand, we can now calculate the network ID, broadcast ID, and host range.
- For the first network, the network ID is equal to the base network. For subsequent networks, the network ID is determined by adding the block size, 64, to the previous network ID.
- The broadcast ID for each subnet is one less than the network ID of the next subnet.
- Finally, The host range for each subnet is from one less than the network ID to one less than the broadcast ID.

| First Subnet | |
|-----------------------------------------------|----------------------------|
| Network ID | 192.168.1.0 |
| Broadcast ID | 192.168.63 |
| Host range | 192.168.1.1-192.168.62 |

| Second Subnet | |
|-----------------------------------------------|----------------------------|
| Network ID | 192.168.1.64 |
| Broadcast ID | 192.168.1.127 |
| Host range | 192.168.1.65-192.168.1.126 |

| Third Subnet | |
|-----------------------------------------------|----------------------------|
| Network ID | 192.168.1.128 |
| Broadcast ID | 192.168.191 |
| Host range | 192.168.1.129-192.168.190 |

| Fourth Subnet | |
|-----------------------------------------------|----------------------------|
| Network ID | 192.168.1.192 |
| Broadcast ID | 192.168.1.255 |
| Host range | 192.168.1.193-192.168.1.254 |

4. Initiated VLAN creation using the CLI on the switch.
- Selected the desired range of VLANs.
- Configured the selected ports into switchport mode.
- Created VLANs within the selected range.
![image](https://github.com/WesleyKProfile/Small-Network-Lab/assets/168662972/209c518b-a2fa-45ee-b45d-ba99899c51d1)
<sub>*ref 4. the command line entries used to create the four subnets*<\sub>

![image](https://github.com/WesleyKProfile/Small-Network-Lab/assets/168662972/1a6f2577-07dd-4323-b28c-7558d453aa33)
<sub>*ref 5. the none server VLANs can be seen on the CLI*<\sub>

5. Configured Access Points (APs) by assigning names and passwords. Implemented WPA2-PSK security protocol to ensure encrypted Wi-Fi communication.
![image](https://github.com/WesleyKProfile/Small-Network-Lab/assets/168662972/bbd1b47b-df37-48d1-a302-6f35d8c48eb2)
<sub>*ref 6. the configuration of the APs*<\sub>

6. Enabled trunking on the switch to allow the transmission of multiple VLANs over a single link.
![image](https://github.com/WesleyKProfile/Small-Network-Lab/assets/168662972/bf3d291e-ab93-43ba-b0d6-24b58c6e4cca)
<sub>*ref 7. CLI entries to enable trunking on the switch*<\sub>

7. Activated the router to establish network connectivity and routing functionality.

8. Configured three subinterfaces to facilitate routing between multiple VLANs.
![image](https://github.com/WesleyKProfile/Small-Network-Lab/assets/168662972/d9a84c9d-1672-4e8e-94a9-f297c125bde7)
<sub>*ref 8. the three subinterfaces for the three department VLANs*<\sub>

9. Activated DHCP (Dynamic Host Configuration Protocol) to dynamically assign IP addresses and network configuration to client devices.

10. Established DHCP pools for each subnet by defining the network, assigning IP addresses, configuring default gateway, DNS servers, and domain information.
![image](https://github.com/WesleyKProfile/Small-Network-Lab/assets/168662972/df454cfb-d2dd-405d-bd14-a0b15d2ac839)
<sub>*ref 9. CLI entries to create DHCP pools*<\sub>

11. Enabled DHCP service on all devices to automate the assignment of IP addresses and network configuration to connected devices.

12. Connected a laptop to each department VLAN through the Access Point (AP) to enable network access within each department's designated network segment.
![image](https://github.com/WesleyKProfile/Small-Network-Lab/assets/168662972/47b8575e-4c2b-4edd-8c39-c1b22a9abc02)
<sub>*ref 10. network with newly deployed laptops*<\sub>

13. Verified network functionality by conducting ping tests to confirm connectivity and assess network responsiveness.
![image](https://github.com/WesleyKProfile/Small-Network-Lab/assets/168662972/a524561e-fa43-4b44-a43f-3ff66abf652d)
<sub>*ref 11. ping command being used to test network functionality*<\sub>

14. Connected an email and file server to the switch and segregated them into their own VLAN for enhanced network security and resource management.

15. Established connectivity between the network and the internet to enable access to external resources and services.
![image](https://github.com/WesleyKProfile/Small-Network-Lab/assets/168662972/b11cb2e9-a010-4ebd-bf88-24cfb44517bf)
<sub>*ref 12. final network topology showcasing network infrastructure and connectivity*<\sub>








