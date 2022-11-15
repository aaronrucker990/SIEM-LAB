<p align="center">
<img src="https://i.imgur.com/hx4TXLv.jpg" height="80%" width="80%" alt="VPN logo"/>
</p>    
    
<h1>Failed RDP to IP Geolocation Information</h1>

This tutorial outlines the implementaion of configuring and observing a VPN, within a Virtual Machine.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- VPN

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)

<h2>Description of Detailed Steps</h2>

Section 1

Generating your Virtual Machine within Microsoft Azure

1. Create a text file or note pad to keep track of your information.
2. Browse to  https://whatismyipaddress.com/ and take note of your IP Address
3. Create a Virtual Machine (You can create a Resource Group when creating your vm)
4. Create Virtual Machine in a  country (try your country or a country close, so your vm isn’t too slow)

	  a. Log into your VM, you created via Remote Desktop
	
	  b. Browse tohttps://whatismyipaddress.com/  and take note of your IP Address

Section 2

Create an account with Proton VPN

5. When creating your account with Proton VPN make sure you sign up for the free version.  https://account.protonvpn.com/signup?plan=free&language=en  
6. Download Proton VPN client within your VM, after creating your account. 

	  a. Sign In to your VPN and choose a server in another country (such as Japan)
	 
	  b. Browse to https://whatismyipaddress.com/   and take note of your IP Address (Your IP Address is now different)
7. Try browsing over to Disney, Google or what ever browser you choose to pick. There may be difference in the sites, becuase of the change in your server. For example when browsing over to Disney the lanuguage was in Japanese, due to the server I chose. 

Section 3

Cleaning up your Virtual Environment

8. Delete the Virtual Machine along with the Resource Group that was created. 
9. Please ensure that you delete all of your resources. 


<h1>Observing Visual Configurations</h1>


<h2>Visual 1</h2>

<p>
<img src="https://i.imgur.com/924SVlu.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Once you browse to www.whatismyipaddress.com you can observe the personal IP Addresss and how it shows the current locatation. You also can observe how my location is currently in Dallas, Texas, from my personal computer.

</p>
<br />


<h2>Visual 2</h2>


<p>
<img src="https://i.imgur.com/WwztYA0.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

You now want to create our Windows 10, Virtual Machine. 

Note : If you create a Virtual Machine in Azure it will automatically create your Resouce Group, as long as you click new Resource Group when creating your virtual Machine. 

</p>
<br />

<h2>Visual 3</h2>


<p>
<img src= "https://i.imgur.com/4VdZdCq.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
    
Now when you remote into your Virtual Machine, please take into account that you have to remote into the public IP Address. If you notice in the visual you can see how the public IP Address has a circle around it. 

</p>
<br />


<h2>Visual 4</h2>

<p>
<img src="https://i.imgur.com/qj4IPRc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Once logged in to Remote Desktop use the Public Ip Address from the the Virtual Machine, to remote into your Virutal Machine. 

</p>
<br />


<h2>Visual 5</h2>


<p>
<img src="https://i.imgur.com/2SRR3lt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
    
You should see this a screen similar to the visual once you have successfully logged in to your Virtual Machine.
    
</p>
<br />

<h2>Visual 6</h2>


<p>
<img src= "https://i.imgur.com/d0ArxCU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
    
Now when browsing to www.whatismyipaddress.com your personal IP Addresss should be the location of the Virtual Machine. It should be different from the personal IP Address that you had, before you entered into your Virtual Machine via RDP.

Note : Make sure you create your Virtual Machine in your region or close. I accidentally created a Virtual Machine in the Asian Pacific region but the lab was still successful. 

    
</p>
<br />

<h2>Visual 7</h2>

<p>
<img src="https://i.imgur.com/HHr1jfj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
    
In this lab you are able to use any type of VPN, but for the sake of convenience you can use Proton Vpn for free. Browse to https://proton.me/ to download the free Proton VPN. 

</p>
<br />


<h2>Visual 8</h2>


<p>
<img src="https://i.imgur.com/dYqCSJI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
    
Once Proton VPN is downloaded you can connect to the country you prefer, but for this lab if you examine I chose a Japan Server. 
    
</p>
<br />

<h2>Visual 9</h2>


<p>
<img src= "https://i.imgur.com/kGSXwad.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
    
Now when browsing to www.whatismyipaddress.com your Virtual Machine's IP Addresss will change according to which server you chose. You can choose any server for this lab, however in this lab you can see that I chose a server in Japan. 

    
</p>
<br />



<h2>Visual 10</h2>


<p>
<img src= "https://i.imgur.com/nYMA9sT.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

If you browse to a site like Google, Disney, or Amazon, you should see a language change depending on what country's server you chose. (I chose a Japan server as demostrated in the visual)
	
</p>
<br />



<h2>Visual 11</h2>


<p>
<img src= "https://i.imgur.com/kJtQNLa.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Make sure you can you clean your up your lab. Please do not to forget to delete your Virtual Machine, so it does not run up your bill in Microsoft Azure.

</p>
<br />



