

![image](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/aca1f23a-907f-41f5-82c4-710fe3daceb2)





<h1>Building and Hosting a Minecraft Server on a Raspberry Pi</h1>

<h2>Project Summary</h2>
This project involves the creation of a Minecraft server on a Raspberry Pi 4 using the Linux command line. Specifically, to download the Minecraft server on our Pi, we will be using the Nukkit software from CloudBurst. Minecraft servers can be used to allow friends to collaborate within the same Minecraft world. Additionally, building a server can allow individuals to customize their own world, as well as adjust settings within the server and fix any problems that may arise. This project can give an introductory view into running and maintaining a server, which is an essential skill for individuals pursuing Information Technology careers. 
<h2>Platforms and Technologies Used</h2>

- Raspberry Pi 3 or 4 (Earlier versions can be used but will lack in performance)
- Ethernet cable (Wi-Fi will be slower than a wired connection)
- 16 GB+ microSD card
- USB or wireless keyboard or mouse 
- Computer monitor 
- HDMI cable 
- Copy of Minecraft Bedrock Edition (will not work on Java)


<h2>Operating Systems Used </h2>

- Raspbian OS

<h2>Project Installation Steps</h2>

- Step 1
  - Find out the IP address of our Raspberry Pi
  - Enter the "sudo hostname -I" command into the bash terminal
    - Additonally, you can enter in the "ifconfig | grep inet" command to find the device IP address as well
  - If the account you are using does not have "sudo" permissions, switch to the root account via the "su root" command
    - Then, enter the root password
    - Once you are in the root account, use the "sudo usermod -aG sudo (username)" command to grant sudo permissions - place the user's name in the username sections of the command
    - Exit the root account with the "exit" command
![Minecraft1](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/99bc462b-356a-4d4c-8f5c-1c8f46476f02)
![MCPhoto2](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/85fec711-29ca-4bff-ad0c-ca1097432614)
![MCPhoto3](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/9e126593-9cd9-4a1c-98a1-d09790a5e6db)
![MCPhoto4](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/ba852fd5-37d1-4e2d-b5be-5e97aac47ba8)


- Step 2  - Before installing any software, make sure to update your Pi with the "sudo apt update && sudo apt upgrade" command via the bash terminal
  ![Photo2](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/9a843670-1f5a-4222-a337-7d168963f6a0)
  - Now, we need to install Java in order for the Nukkit server software to deploy 
    - Enter in the "sudo apt install default-jdk" command
    - When prompted to download, make sure to type "Y" and press enter 
    - ![MCPhoto5](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/dce5de74-1e9d-4f78-b5bf-f72e9d933501)

  ![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/baef5b4a-f3ed-40d2-90d6-fcd570da6d1c)

- Step 3
  - Repeat the same process and create a Virtual Machine with an Ubuntu Server Image
  - Make sure that both Virtual Machines are on the same Virtual Network   
![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/c12876b3-2705-4d20-a23a-297d160110e4)



- Step 4
  - Utilizing RDP on Windows, remote into Virtual Machine 1 (Windows Pro) - by typing in the IP Address
  - If using a Mac computer, go to the app store and download the Microsoft Remote Desktop application
  - You will be prompted with a login screen - use the credentials you provided during the virtual machine creation process
![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/6d103328-f103-429d-aef5-f47c17e1aa1b)


- Step 5
  - Once you are booted into the Virtual Machine, proceed to download Wireshark
  - Type in "Download Wireshark" on a Google Search
    ![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/0fb98c1c-7feb-4465-8ba6-9e4914726d40)

- Step 6
  - Once you are finished downloading Wireshark, boot up Wireshark by searching for the program towards the bottom left corner of the screen
  
   ![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/4929ebc0-2736-48f7-bec3-81b7cb40ae7a)

- Step 7
  - Once you are in Wireshark, be sure to select Ethernet
  ![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/f4463c38-3339-439e-9e2c-1ce43ee360a5)

- Step 8
  - You will begin to see multiple streams of network traffic be displayed
  - Above the network traffic, where it says "Apply a Display Filter" in the white box, type in whatever traffic you would like to be displayed
  - Have fun analyzing network traffic!
  - ![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/bd4a5ea6-9da4-4706-8a86-364312b0e281)

<h2>Project Demonstration</h2>

<p>

![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/0671b969-85bd-41ab-bcf3-0f04519b67ac)
  - We can see there is a connection established between VM1 and VM2 via the non-stop ping command
    - ping 10.0.0.5 -t
      - This command can be entered into command prompt by typing "cmd" in the start menu below
        - Make sure that before clicking cmd, right-click and select "run as administrator"
- 10.0.0.5 is the private IP Address of our Linux Virtual Machine

![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/aecc41e7-943b-488c-91b5-9365e1bfb142)
- We will now block this connection by going back to Microsoft Azure, and typing in "Network Security Groups" into the search bar
- On the left, we can click the "Inbound Security Rules" tab, and click the add button - this tab is selected because we want to block any ICMP traffic coming into VM2, hence the word "inbound"
- Be sure to select ICMP as the protocol and the deny option
  - ICMP stands for Internet Control Message Protocol, and is the protocol that is used when using the ping command
- Lastly, select the add button, and the security rule will be created

![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/ca61784b-48d5-4c3d-86fc-db57538c90a9)
- Now, we can observe that any traffic being sent to VM2 is being blocked

  ![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/25ae8002-6238-4782-bf84-f59863d0d4a3)
- We can reverse this process by going back to our NSG for VM2, selecting the rule we created, and clicking the allow button under ICMP
- Be sure to press "save" and the rule will be created

  ![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/7d98f982-45f0-4928-8eb8-1af9450b4d3b)
- We can see the replies from VM2 coming back after we changed the inbound rule 

![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/dcaf8831-58c9-4eee-8774-a0f187424535)
- Utilizing SSH, we can also acces the Linux terminal of VM2 from VM1
  - To access VM2 using VM1, be sure to input SSH Username@IP Address
    - The username and IP address of the VM that you are trying to access
   
![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/dcec2035-05ec-472a-8a8f-12645b2a06fc)
- Once we filter for Remote Desktop Protocol traffic, we can see the inundation of traffic
  - This is because we are literally using RDP to access our VM
 
  ![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/20ff0139-ebf7-4af2-b4e8-7e5ab8ac5f94)
- After visiting different websites on our VM, we can see all the DNS information on Wireshark
- Additionally after utilizing the command "ipconfig /displaydns", we can see that our cache is full of information

  ![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/4f6a5650-6f0a-46c3-ba8b-602a661b59c9)
- To flush our DNS cache, we can use the "ipconfig /flushdns" command
  - This command is really important when users are experiencing a multitude of DNS issues
 
![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/67e1cf2c-17f3-4859-8201-12f1d177169b)
- To view our DHCP and DNS servers, we can type the command "ipconfig /all" into command prompt

  ![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/e20a6d00-e5f7-4516-9a66-daf11afcfbaf)
- DHCP traffic can be analyzed by using the "ipconfig /release" and "ipconfig /renew" commands
  - The release command will tell our DHCP server to get rid of our current IP address, which was given to us via DHCP
  - The renew command will give us a new allocated IP address that is dynamically given via DHCP
  - Note that when you use these commands, your connection may be lost since we have "released" the VM's current IP address
 
  ![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/cad81990-28a6-4ddd-aea6-5eee091ed677)
  - You can now see in Wireshark, the steps of DHCP release and renewal
    - The DORA process highlights how a Client and DHCP Server communicate
      - Discovery, Offer, Request, and Acknowledge 
      
**** Picture used at the top of personal project is not mine (taken from Google)
