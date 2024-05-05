# Small Network Lab

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
<sub>*ref 1. all hardware, excluding servers and cabling*<\sub>

2. Established wired connections for all devices and organized them into VLAN groups for network segmentation and management.
![image](https://github.com/WesleyKProfile/Small-Network-Lab/assets/168662972/4f5e2a1a-b0f7-4139-819a-2609ed11b0a5)
<sub>*ref 2. colored circles show VLANs to be implemented*<\sub>

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



