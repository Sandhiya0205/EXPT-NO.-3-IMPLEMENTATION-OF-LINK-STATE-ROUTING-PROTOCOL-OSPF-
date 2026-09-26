# EXPT NO.3 IMPLEMENTATION OF LINK STATE ROUTING PROTOCOL OSPF
# AIM

To connect computers in multiple networks using Open Shortest Path First Routing Protocol and to verify the connectivity between computers.

# EQUIPMENTS REQUIRED
<img width="1306" height="655" alt="image" src="https://github.com/user-attachments/assets/df73b26a-075c-4263-9dbc-9e46e02a7e46" />


# IP ASSIGNMENT
<img width="1600" height="845" alt="image" src="https://github.com/user-attachments/assets/d024e48b-37b8-49b6-aa4c-64ac912d9a33" />
<img width="1600" height="1396" alt="image" src="https://github.com/user-attachments/assets/b7b06c62-32ee-44e9-9e6d-64fb1fc41aaf" />



# NETWORK DIAGRAM
<img width="1600" height="812" alt="image" src="https://github.com/user-attachments/assets/d44630fb-fa82-4b8a-b9bf-8caa4bf12524" />

 
# PROGRAM

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
Steps to Check the Output:
1.	Verify RIP Routing Table on Routers
To check if RIP is working and the routes are learned from the other router, you need to inspect the routing table on each router.
Click Router 0
In the same CLI window type this
Router# show ip route
You should see routes for the networks connected to Router1 (192.168.3.0 and 192.168.4.0) via RIP. The output might look something like this:
 
R 192.168.3.0 [120/1] via 192.168.2.2, 00:00:00, FastEthernet0/1
R 192.168.4.0 [120/1] via 192.168.2.2, 00:00:00, FastEthernet0/1
For Router1, enter the same command:
Router# show ip route
You should see routes for the networks connected to Router0 (192.168.1.0 and 192.168.2.0) via RIP:
R 192.168.1.0 [120/1] via 192.168.2.1, 00:00:00, FastEthernet0/0
R 192.168.2.0 [120/1] via 192.168.2.1, 00:00:00, FastEthernet0/0

2.	Ping from PC to PC
You can also check connectivity between the PCs on different networks to ensure that RIP is correctly routing packets across the routers.
•	Example: Ping from PC0 (192.168.1.2) to PC3 (192.168.3.2):
1.	Click on PC0, go to the Desktop tab.
2.	Open the Command Prompt.
3.	Use the ping command: ping 192.168.3.2
4.	If everything is configured correctly, you should receive replies from PC3.
•	Similarly, you can ping between other PCs (e.g., from PC2 to PC5) to verify network connective






# OUTPUT
<img width="1531" height="874" alt="image" src="https://github.com/user-attachments/assets/141eb1b2-bbd0-41eb-885a-aca1f6472871" />
<img width="1600" height="784" alt="image" src="https://github.com/user-attachments/assets/5d7f35f2-4684-4eb9-abbf-b8a47f0f64e0" />





# RESULT
Thus the computers in multiple networks using Open Shortest Path First Routing Protocol is connected and the connectivity between the computers is verified.

