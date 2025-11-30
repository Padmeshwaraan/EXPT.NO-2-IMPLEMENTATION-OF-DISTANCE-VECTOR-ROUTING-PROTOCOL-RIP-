# EXPT.NO-2-IMPLEMENTATION-OF-DISTANCE-VECTOR-ROUTING-PROTOCOL-RIP
# AIM:

To connect computers in multiple networks using Distance Vector Routing Protocol and to verify the connectivity between computers.
# EQUIPMENTS REQUIRED:

<img width="987" height="271" alt="2cn" src="https://github.com/user-attachments/assets/87d3fe0d-3265-4657-8f19-ef8c7f873e5c" />


# IP ASSIGNMENT:
<img width="1022" height="493" alt="22cn" src="https://github.com/user-attachments/assets/24bd084d-9e05-481b-bdfb-db4edd8f5a31" />



# NETWORK DIAGRAM:
<img width="1366" height="768" alt="Screenshot 2025-11-14 090555" src="https://github.com/user-attachments/assets/24cbf465-b7ee-463e-8dac-b425443d7a4a" />

# PROCEDURE:

STEP 1: Open a Packet Tracer Software.<br>
STEP 2: Drag two 2900 Switches, two Cisco 1800 Routers, four PC Terminals from tool barand drop it in work area.<br>
STEP 3: Connect all the PC Terminals and Routers through Switches as shown in the networkdiagram using CAT 6 Patch cables.<br>
STEP 4: Configure IP address and Gateway in all PC Terminals.<br>
STEP 5: Configure ROUTER0 and restart ROUTER0.<br>
STEP 6: Configure ROUTER1 and restart ROUTER1.<br>
STEP 7: Verify the connectivity between PC Terminals in different networks using Pingcommand.<br>
After This follow the given procedure
1. Assign IP Addresses to PCs
•	For each PC, go to Desktop > IP Configuration and assign:
o PC0: 192.168.1.2, Subnet Mask: 255.255.255.0, Gateway: 192.168.1.1<br>
o PC1: 192.168.1.3, Subnet Mask: 255.255.255.0, Gateway: 192.168.1.1<br>
o PC2: 192.168.2.2, Subnet Mask: 255.255.255.0, Gateway: 192.168.2.1<br>
o PC3: 192.168.3.2, Subnet Mask: 255.255.255.0, Gateway: 192.168.3.1<br>
o PC4: 192.168.4.2, Subnet Mask: 255.255.255.0, Gateway: 192.168.4.1<br>
o PC5: 192.168.4.3, Subnet Mask: 255.255.255.0, Gateway: 192.168.4.1<br>
 
# PROGRAM
```

Router0 Configuration Steps
Click Router 0 and in CLI TYPE THIS Router> enable
Router# configure terminal Router(config)# interface FastEthernet0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0 Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# interface FastEthernet0/1
Router(config-if)# ip address 192.168.2.1 255.255.255.0 Router(config-if)# no shutdown
Router(config-if)# exit Router(config)# router rip Router(config-router)# version 2
Router(config-router)# network 192.168.1.0
Router(config-router)# network 192.168.2.0 Router(config-router)# exit

Router1 Configuration Steps
Click Router 1 and in CLI TYPE THIS Router> enable
Router# configure terminal Router(config)# interface FastEthernet0/0
Router(config-if)# ip address 192.168.3.1 255.255.255.0 Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# interface FastEthernet0/1
Router(config-if)# ip address 192.168.4.1 255.255.255.0 Router(config-if)# no shutdown
Router(config-if)# exit Router(config)# router rip Router(config-router)# version 2
Router(config-router)# network 192.168.3.0
Router(config-router)# network 192.168.4.0 Router(config-router)# exit
```
Steps to Check the Output:
1.	Verify RIP Routing Table on Routers
To check if RIP is working and the routes are learned from the other router, you need to inspect the routing table on each router.
Click Router 0<br>
In the same CLI window type this<br>
Router# show ip route<br>
You should see routes for the networks connected to Router1 (192.168.3.0 and 192.168.4.0) via RIP. The output might look something like this:<br>
 
R 192.168.3.0 [120/1] via 192.168.2.2, 00:00:00, FastEthernet0/1<br>
R 192.168.4.0 [120/1] via 192.168.2.2, 00:00:00, FastEthernet0/1<br>
For Router1, enter the same command:<br>
Router# show ip route<br>
You should see routes for the networks connected to Router0 (192.168.1.0 and 192.168.2.0) via RIP:<br>
R 192.168.1.0 [120/1] via 192.168.2.1, 00:00:00, FastEthernet0/0<br>
R 192.168.2.0 [120/1] via 192.168.2.1, 00:00:00, FastEthernet0/0<br>

2.	Ping from PC to PC
You can also check connectivity between the PCs on different networks to ensure that RIP is correctly routing packets across the routers.
•	Example: Ping from PC0 (192.168.1.2) to PC3 (192.168.3.2):
1.	Click on PC0, go to the Desktop tab.
2.	Open the Command Prompt.
3.	Use the ping command: ping 192.168.3.2
4.	If everything is configured correctly, you should receive replies from PC3.
•	Similarly, you can ping between other PCs (e.g., from PC2 to PC5) to verify network connective
 
# OUTPUT
![WhatsApp Image 2025-11-27 at 09 43 29_19a93b42](https://github.com/user-attachments/assets/29f9a974-a32e-4adf-9fb9-8bdb67861bc4)


<img width="1366" height="766" alt="Screenshot 2025-11-14 091037" src="https://github.com/user-attachments/assets/f2398daf-f435-4cdf-83cc-d94d4b31f256" />


# RESULT:

Thus the computers in multiple networks using Distance Vector Routing <img width="576" height="365" alt="image" src="https://github.com/user-attachments/assets/f4245c26-a2f8-4621-b317-0a2c8049f764" />
