

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


- Step 3
  - We will now need to create a directory for our Minecraft server
  - Enter in the "sudo mkdir minecraftserver" command and press enter 
![MCPhoto7](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/64c745e1-3fe5-474e-a18e-04f434f87003)
  - Now that we have made our directory for the Minecraft server, we have to go into that directory
  - In order to change directories, we will use the "cd minecraftserver" command to go into the directory 
  ![MCPhoto8](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/1b467b68-142b-4504-8f89-4c9946748de3)
  - As you can see within the terminal, we are in our Minecraft server directory 


- Step 4
  - We will now need to download the software for our Nukkit server and can do this in our terminal
  - Go ahead and copy and paste this long command and make sure to use "sudo" before entering this command:wget -O nukkit.jar https://ci.opencollab.dev/job/NukkitX/job/Nukkit/job/master/lastSuccessfulBuild/artifact/target/nukkit-1.0-SNAPSHOT.jar
 ![MCPhoto9](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/6a8406f9-02f8-4e78-bca9-ec8b9a348f42)




- Step 5
  - Since we have downloaded the Nukkit server software, it is time to deploy the server
  - In order to deploy the server, enter in the "sudo java -jar nukkit.jar" command and choose your desired language
![MCPhoto10](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/f6306b26-9ff6-4a37-b42b-7b8408b96fb2)


- Step 6
  - Our server is now being configured with the appropriate settings
  - Take note of the port that our server is running on
  - Do not worry about the 0.0.0.0 for the IP address we can change this or keep it as is
  ![MCPhoto11](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/4b8c7f2b-5d31-459a-8e45-306f773efbe1)


- Step 7
  - For us to configure settings within our own server, we need to stop the server
  - This can be accomplished by entering "stop" while our server is running 
 ![MCPhoto12](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/8f4e8af7-7dfd-495c-821e-279f8d819797)


- Step 8
  - We need to open our server properties file to configure settings
  - Enter the "sudo nano server.properties" command - nano is a text editor used in Linux
   ![MCPhoto13](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/db9505ca-1414-447c-8613-b474b2cbc467)
   ![MCPhoto16](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/81cc33ce-f151-4297-8954-d5e7e4118fad)
  - As you can see, I have changed the IP address to match my Raspberry Pi device, and keep the port number the same
  - Take note of the many different settings that can be configured within this server
  - To save changes and leave the nano text editor, press "Ctrl-X, Y, and enter"
 

- Step 9
  - We are now back to our bash terminal and need to start our Minecraft server again
  - Run the "sudo java -jar nukkit.jar" command 
  ![MCPhoto15](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/c8608724-0060-477b-9e9e-7bca94a833c8)
  ![MCphoto17](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/89edd283-a484-42d7-8d1b-83a459968067)
  - The Minecraft server is up and running on the specified IP address
  - Before connecting to the Minecraft server, make sure that port 19132 is allowed if you have a firewall
    - In my case, I have UFW (Uncomplicated Firewall) installed on my Pi and needed to allow port 19132 to connect to the Minecraft server
   
      
    ![MCPhoto18](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/0b537aa8-aeff-4712-8cd5-48581a2c231c)



- Step 10
  - Load up Minecraft Bedrock edition and navigate to the add "Add External Server" section of the game 
  - Enter the appropriate details such as the server name, address, and port number
  - Click "Play"
    ![MCPhoto19](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/9fbb7f93-bad5-4957-9420-bb925cb2c380)
    ![MCPhoto20](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/dcf53a3e-54d6-4440-9672-c0c1d72d0847)
    - The Minecraft world has been loaded, and we are playing in our newly created Minecraft server
    - Stop the server anytime by entering stop into the Linux command line 
    ![MCPhoto22](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/323075ec-6ad3-434f-8a48-31332ad70c76)
    ![MCPhoto21](https://github.com/chriskhawaja/MinecraftServer/assets/153021794/ec83ef06-212f-4dae-b0ea-cdc49142c16d)




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
