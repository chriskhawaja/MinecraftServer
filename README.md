

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


<h2>Sources and Credit </h2>


- https://www.youtube.com/watch?v=u2DnafpNQW8&t=384s (Zak Jaeb)


- https://www.makeuseof.com/tag/setup-minecraft-server-raspberry-pi/ (Christian Cawley)

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

IMPORTANT - It is essential to secure any server you have working on your system
I recommend downloading a firewall onto your Pi such as UFW (Uncomplicated Firewall) and an Anti-Malware program such as Clam AV
I hold no responsibility for any print server that is unsecure, make sure to secure your server!
      
**** Picture used at the top of personal project is not mine (taken from Google)
