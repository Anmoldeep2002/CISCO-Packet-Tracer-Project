<h1>Small Office Network Design and Configuration with DHCP and DNS</h1>


<h2>Description</h2>
<p>This project simulates the setup and configuration of a small office network using Cisco Packet Tracer. It showcases my ability to configure a DHCP server to assign IP addresses to devices across two different subnets, using a router as a DHCP relay. It also demonstrates my ability to set up DNS for hostname resolution, and manually configure static IP addresses on router interfaces. This configuration is widely used in real-world small and medium-sized organisations to centralize IP address management and ensure scalability.</p>


<br />

<h2>Environments Used</h2>

- <b>Cisco Packet Tracer</b>

<h2>Tools Used</h2>

- <b>Cisco 2911 (Router)</b> 
- <b>Cisco WS-C2960-24TT (Switch)</b>
- <b>Cisco Access Point (AP)</b> 
- <b>Cisco Server</b>
- <b>Laptop</b>
- <b>PC</b>

<br />

<h2>Step-by-Step Walk-Through:</h2>

<p align="center"> 
STEP 1 (CREATING NETWORK DESIGN): <br/>
<img src="https://i.imgur.com/CYTRd2m.png" height="70%" width="70%"/> </p>


<p align="center">This is the design I created for my project using Cisco Packet Tracer software. As you can see, the network is made up of one router, two switches, four clients, one access point, and one server. This network design was created for a small office that is divided into two rooms (ROOMS 1 and 2). Each room contains one switch and two clients, with ROOM 1 featuring an "Access Point" for wireless connectivity. The router has been put in the middle to facilitate communication between the two rooms, which are on different subnets. The server handles DHCP and DNS duties, and clients can automatically receive IP addresses from an IP pool. The server will also allow clients to "PING" each other by simply entering the device name rather than an IP address.</p>


<hr width="100%" size="2">

<br />

<p align="center"> 
STEP 2 (CONNECTING DEVICES): <br/>
<img src="https://i.imgur.com/SDEVZUi.png" height="70%" width="70%"/> </p>


<p align="center">The following step was to connect all of the devices and clients together. First, I selected the option to connect the devices, followed by the port to which the device would be connected. The second image shows that all of the devices and clients (with the exception of the laptop) are connected to their appropriate ports via an ethernet cable.</p>


<hr width="100%" size="2">

<br />

<p align="center"> 
STEP 3 (ENABLING ROUTER INTERFACES): <br/>
<img src="https://i.imgur.com/SDEVZUi.png" height="70%" width="70%"/> </p>


<p align="center">On startup, some of the interfaces are disabled, as indicated by the colour "Red" next to the device ports. The router ports are disabled by default upon startup and must be manually enabled. All of the other devices' interfaces are already activated upon startup.</p>


<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/X9ulCI3.png" height="50%" width="50%"/> </p>


<p align="center">I'm using the router's command line interface. This will allow me to make adjustments to the router and therefore activate the appropriate interfaces.</p>


<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/VZy1Cbk.png" height="60%" width="60%"/> </p>


<p align="center">I've set the router to "ENABLE" mode.</p>


<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/4GeiQJR.png" height="60%" width="60%"/> </p>


<p align="center">I've enabled "CONF T" mode on the router. This option will allow me to change the router configurations based on the project requirements.</p>


<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/8yVcmjT.png" height="60%" width="60%"/> </p>


<p align="center">I can use the command "INT RANGE" to access various interfaces (g0/0, g0/1, and g0/2) without having to configure them individually. After I gained access to the interfaces, I executed the "NO SHUT" command. This command allowed me to manually enable the router's selected interfaces.</p>


<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/I5ZxBZo.png" height="70%" width="70%"/> </p>


<p align="center">As shown in the router's CLI, the specified interfaces have been enabled, and their current status is "UP".</p>



<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/qLVTddA.png" height="70%" width="70%"/> </p>


<p align="center">The router's interfaces are now enabled, as shown in the picture, with all of them coloured green. </p>


<hr width="100%" size="2">

<br />

<p align="center"> 
STEP 4 (ASSIGNING IP ADDRESS RANGE): <br/>
<img src="https://i.imgur.com/kKaBbOZ.png" height="90%" width="90%"/> </p>


<p align="center">In this stage, I assigned IP address ranges to the two separate rooms. Each room is on a separate subnet. Room 1 is in the 192.168.1.0 subnet, whereas Room 2 is in the 192.168.2.0 subnet.</p>


<hr width="100%" size="2">

<br />

<p align="center"> 
STEP 5 (MANUALLY ASSIGNING IP ADDRESSES ON ROUTER): <br/>
<img src="https://i.imgur.com/dMqlYch.png" height="90%" width="90%"/> </p>


<p align="center">I've selected which IP addresses to add to the router's Gig0/0 and Gig0/1 interfaces. These are the interfaces that will serve as the default gateways for the two separate rooms. These interfaces will allow the two rooms to communicate with one another and the server.</p>


<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/St8U0zf.png" height="70%" width="70%"/> </p>


<p align="center">Here, I've assigned an IP address to the GIG0/0 interface, which faces ROOM 1. I chose the interface to configure with the command "INT G0/0" and assigned the IP address with the command "IP ADDRESS 192.168.1.100" followed by the subnet mask "255.255.255.0". Clients in ROOM 1 can now communicate with external clients across different subnets.</p>


<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/rWCbgly.png" height="70%" width="70%"/> </p>


<p align="center">Here, I've assigned an IP address to the GIG0/1 interface, which faces ROOM 2. I chose the interface to configure with the command "INT G0/1" and assigned the IP address with the command "IP ADDRESS 192.168.2.100", followed by the subnet mask "255.255.255.0". Clients in ROOM 2 can now communicate with external clients across different subnets.</p>


<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/vekDONL.png" height="70%" width="70%"/> </p>


<p align="center">Here's the end result after assigning IP addresses to the router's "GIG0/0" and "GIG0/1" interfaces. As you can see, I used the router's "show ip interface brief" command to ensure that the IP addresses were actually assigned correctly. I can also see that the interfaces are "UP", which means they are "ACTIVE" and have not been shut down.</p>



<hr width="100%" size="2">

<br />

<p align="center"> 
STEP 5 (MANUALLY ASSIGNING IP ADDRESSES ON ROUTER (PART 2)): <br/>
<img src="https://i.imgur.com/cITIY6n.png" height="70%" width="70%"/> </p>


<p align="center">In the diagram, I've assigned the IP address range for the router-to-server link. The server is in a separate room, therefore it will be on a different subnet. Both the router and the server will be on the subnet 200.0.0.0.</p>


<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/UxHVPYz.png" height="70%" width="70%"/> </p>


<p align="center">I've assigned an IP address to the interface "GIG0/2" that is facing the server. I've assigned the IP address of "200.0.0.2" and the subnet mask "255.255.255.252".</p>


<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/NkvE2Bf.png" height="70%" width="70%"/> </p>


<p align="center">I've used the command "SHOW IP INTERFACE BRIEF" to confirm that the interface "GIG0/2" has been given the correct IP address.</p>


<hr width="100%" size="2">

<br />

<p align="center"> 
STEP 6 (ASSIGNING IP ADDRESS TO SERVER): <br/>
<img src="https://i.imgur.com/bStHcC2.png" height="70%" width="70%"/> </p>


<p align="center">I proceeded to the server configuration mode, and the procedure of giving IP addresses to clients and servers is a little different because this is a "Simulating Software". For the server, I've assigned an IP address of 200.0.0.1 and a subnet mask of "255.255.255.252". I've also set a default gateway with the IP address "200.0.0.1" for the router's "GIG0/2" interface.</p>

<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/q1v6EDI.png" height="70%" width="70%"/> </p>


<p align="center">I'm on the server's "Command Prompt" and have used the "IPCONFIG" command to check if the IP address has been configured. The IP address was successfully set.</p>


<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/isYQ4K5.png" height="70%" width="70%"/> </p>


<p align="center">I pinged the router interface that was facing the server. I've used the "PING" command to ping the IP address 200.0.0.2. The pings were successful, indicating that the server can reach transmit data to the router.</p>

<hr width="100%" size="2">

<br />

<p align="center"> 
STEP 7 (CONFIGURING DHCP): <br/>
<img src="https://i.imgur.com/cDRQI1y.png" height="70%" width="70%"/> </p>


<p align="center">Here, I've accessed the server's DHCP settings. As you can see, I have plenty of choices for configuring a DHCP pool, including adding a custom pool name, a range of IP addresses, and the number of clients who can obtain an IP address. I've also enabled the DHCP server by selecting "Service ON".</p>


<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/jokbX1P.png" height="70%" width="70%"/> </p>


<p align="center">Here, I've set up a DHCP pool for ROOM 1. I named the pool "Subnet 1" to make it clear that it is for ROOM 1. I assigned the pool a range of 10 IP addresses for clients. The pool will begin with the IP address 192.168.1.1 and end with 192.168.1.10. I've set the default gateway to the router's G0/0 interface, which means that all clients in ROOM 1 will be automatically issued this default gateway, as well as a random IP address and the DNS server.</p>


<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/rk2zgjV.png" height="70%" width="70%"/> </p>


<p align="center">Here, I've set up a DHCP pool for ROOM 2. I titled the pool "Subnet 2" to make it clear that it is for ROOM 2. I assigned the pool a range of 10 IP addresses for clients. The pool will begin with the IP address 192.168.2.1 and end with 192.168.2.10. I've set the default gateway to the router's G0/1 interface, which means that all clients in ROOM 2 will be automatically given this default gateway, as well as a random IP address and the DNS server.</p>



<hr width="100%" size="2">

<br />

<p align="center"> 
STEP 8 (CONFIGURING DHCP RELAY): <br/>
<img src="https://i.imgur.com/OPtyqUb.png" height="50%" width="50%"/> </p>


<p align="center">I'm currently at the "command prompt" of PC1, which is in Room 2's network. As you can see, I used the "ipconfig" command to check whether the client has received IP address from the DCHP server. It has not yet been assigned an IP address.</p>


<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/gqmV5PR.png" height="70%" width="70%"/> </p>


<p align="center">I attempted to obtain an IP address from the DHCP server, but it failed to assign one. I used the "IPCONFIG /RENEW" command, which lets devices obtain IP addresses from the server. The error message displayed was "DHCP REQUEST FAILED".</p>


<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/VE7biR8.png" height="70%" width="70%"/> </p>


<p align="center">Here I'm attempting to resolve the previous issue in which the client in ROOM 2 was not being allocated an IP address by the DHCP server. To resolve this issue, I had to go to the router's CLI and configure it from there. I had to access the G0/1 interface, which serves as the default gateway for ROOM 2. Once accessed, I had to use the "IP HELPER-ADDRESS" command, which is very useful since it allows the router to forward "DHCP REQUEST" messages from clients to the server. It will send the messages to the DHCP server's IP address, 200.0.0.1.</p>


<hr width="100%" size="2">

<br />

<p align="center"> 
STEP 9 (Configuring IP address for PC's): <br/>
<img src="https://i.imgur.com/ytrntUs.png" height="70%" width="70%"/> </p>


<p align="center">I'm back on PC 1 and I tried again to request an IP address using the "IPCONFIG /RENEW" command. As you can see, the IP request was successful, and the DHCP server assigned an IP address to PC1. The assigned IP address is 192.168.2.1.</p>


<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/qFGEXom.png" height="70%" width="70%"/> </p>


<p align="center">I'm on PC 2 and I tried again to get an IP address using the "IPCONFIG /RENEW" command. As you can see, the IP request was successful, and the DHCP server assigned an IP address to PC2. The assigned IP address is 192.168.2.2.</p>


<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/G47Tiqt.png" height="70%" width="70%"/> </p>


<p align="center">Here, I'm pinging ROOM 2's default gateway from PC1. As you can see, the pings were successful, and there is full connectivity between the clients and the router.</p>


<hr width="100%" size="2">

<br />

<p align="center"> 
STEP 9 (Configuring DNS): <br/>
<img src="https://i.imgur.com/emswEgx.png" height="70%" width="70%"/> </p>


<p align="center">Here, I accessed the server's DNS services. Both DCHP and DNS are configured on a single server, allowing me to control both operations from a single device. As you can see, I've enabled DNS services, which will allow me to assign IP addresses to names that are easy to read. In this scenario, I will assign names to the clients' IP addresses from ROOM 2. This allows other clients to ping them simply by inputting the device's name rather than its IP address.</p>


<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/VXDRd6b.png" height="70%" width="70%"/> </p>


<p align="center">As you can see, I've assigned the name "PC1" to pc1's IP address using the DNS server. This allows other clients to ping this specific device by just typing "PING PC1" from the "command prompt". IP address 192.168.2.2 now goes under the name "PC1".</p>


<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/q8dm2sE.png" height="70%" width="70%"/> </p>


<p align="center">I've assigned the name "PC2" to PC2's IP address from the DNS server. This allows other clients to ping this specific device by just typing "PING PC2" from the "command prompt". IP address 192.168.2.1 now goes by the name "PC2".</p>


<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/gPAu8GK.png" height="50%" width="50%"/> </p>


<p align="center">Now I can ping PC1 by typing its precise name rather than its IP address. This is more convenient and easier for humans to remember. I ran the "PING PC1" command, and all of the pings got through. The DNS request was successful.</p>


<br />
<br />

<p align="center"> 
<img src="https://i.imgur.com/6Cp0Hx2.png" height="50%" width="50%"/> </p>


<p align="center">Now I can ping PC2 by typing its precise name rather than its IP address. This is more convenient and easier for humans to remember. I ran the "PING PC2" command, and all of the pings got through. The DNS request was successful.</p>



















