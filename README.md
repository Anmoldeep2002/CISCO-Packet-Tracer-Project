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










































