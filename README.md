# Configure A Web Server with Azure

In this project, we will use Microsoft Azure Cloud to create a resource group, a virtual Network & subnet, a virtual machine and configure Windows Web server IIS. This is the first Azure project I am uploading and I plan to use Azure for more complicated projects in the coming weeks.

# Systems Used

### Microsoft Azure Cloud

### Windows Server 2022 Virtual Machine


# **Step 1: Planning**

### Model
The following model is what we will be following when setting up and configuring our resources.

<img src="https://i.imgur.com/5b2wvSO.png" height="80%" width="80%" alt="Model Architechture"/>

### Create an Azure Account
Before this project, you must have a Microsoft Azure account. A free trial is availble [here](https://azure.microsoft.com/en-us/pricing/offers/ms-azr-0044p) for new users and this will be sufficient for this project.

# **Step 2: Create Virtual Network**

### Create Virtual Network
From our home page we will click the + sign near the top to create a new resource. In the search bar type, "Virtual Network". Select the option called **Virtual Network** and you should arrive at a page shown below. We are going to name our Virtual Netwok "AWS-VNet". This stands for "Azure web server" and we will continue to use this name for our other resources for simplicity and ease of readability.
* **Make sure to create a new resource group if needed** - If you dont already have a resource group, use the blue text option to create a new resource group here that we will use for this project.
* Select a region that corresponds with your geographical location
* We can activate security features on the next tab such as "Virtual Network Encryption", "Azure Bastion", "Azure Firewall" and "Azure DDoS Protection". These are useful but for this demo they will not be necessary and they can increase cost.

<img src="https://i.imgur.com/7V82EYP.png" height="80%" width="80%" alt="VNET1"/>

### Create Subnet
Navigate to the **IP Addresses** tab at the top of the page or by hitting next until you arrive at the correct tab. Configure the subnet as shown below and hit save. These settings will be fine for now. Make sure to press **Review + Create** at the bottom and the virtual nework and will begin to deploy.

<img src="https://i.imgur.com/dsKFHYs.png" height="80%" width="80%" alt="Subnet1"/>

# **Step 3: Create VM**

### Create Windows Server Virtual Machine
Create another resource in the same way as before but this time search for "Virtual Machine" and click the option called **Virtual Machine**.
* Make sure to select the Resource Group
* Select the same region that you selected before
* For this project the availablitiy option "no infrastructure redundency required" is selected
* Any Windows Server VM should work for this project but we are choosing the 2022 version
* Choose an appropriate size for your Machine (The standard B1 size should be sufficient for this project but there were none available for my region so I selected a larger size than necessary)
* Choose secure credentials that you will remember

<img src="https://i.imgur.com/BbiZZHs.png" height="80%" width="80%" alt="VM1"/>
<img src="https://i.imgur.com/2yZGMXw.png" height="80%" width="80%" alt="VM2"/>
<img src="https://i.imgur.com/k4LlU1y.png" height="80%" width="80%" alt="VM3"/>

### Allow Ports and Review + Create
We are going to allow port 443 and 3389 for this project but you can select other ports if you want them (such as port 80). We will need to use port 3389 which is remote desktop protocol and port 443 is for HTTPS. For this project the rest of the options will be left as default but feel free to look through them before selecting **Review + Create**.

<img src="https://i.imgur.com/c2gPTQD.png" height="80%" width="80%" alt="VM4"/>


# **Step 4: Configure Windows IIS on Virtual Machine**

### Connect to VM with Remote Destop Connection
Once the VM has finished Deploying we can click on and locate the **Public IP address** and copy that IP to our clipboard. Next, on our windows machine, we type "Remote Desktop Connection" into the start menu search bar. Once prompted, paste the IP address into the pop up and then enter your credentials from the previous step.

<img src="https://i.imgur.com/KZABiZS.png" height="80%" width="80%" alt="VM5"/>
<img src="https://i.imgur.com/yJMgNrP.png" height="80%" width="80%" alt="RDP1"/>
<img src="https://i.imgur.com/fs1hRV7.png" height="80%" width="80%" alt="RDP3"/>

### Configure Windows IIS
The Windows VM may take a minute to fully launch but when it does, the **Server Manager** should automatically launch. If not, it can be manually launch from the start menu. We need to Click **Add roles and features** and click next until we reach the **Server Roles** page. Scroll down and select **Web server (IIS)** and then press add feature. From here we can simply click next until the final page and press install.

<img src="https://i.imgur.com/0m8fWdH.png" height="80%" width="80%" alt="RDP4"/>
<img src="https://i.imgur.com/pR7VAYt.png" height="80%" width="80%" alt="RDP5"/>

# **Step 5: Test Our Web Server**

###Web page test
Once the installation is complete we can type our public ip address into a web browser and we should see the following. From here we could take code from a developer and deploy it on this web server.

<img src="https://i.imgur.com/PdAWpGO.png" height="80%" width="80%" alt="Windows Server IIS"/>


# Conclusion

In this project we have used Microsoft Azure Cloud to create a resource group, Virtual Network & Subnet, a virtual machine and we have configured Windows Web server IIS from that VM. 
