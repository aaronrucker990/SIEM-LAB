<p align="center">
<img src="https://i.imgur.com/hx4TXLv.jpg" height="80%" width="80%" alt="VPN logo"/>
</p>    
    
<h1>Failed RDP to IP Geolocation Information (SIEM LAB)</h1>

The Powershell script in this repository is responsible for parsing out Windows Event Log information for failed RDP attacks and using a third party API to collect geographic information about the attackers location.<br />

<h2>Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- PowerShell: Extract RDP failed logon logs from Windows Event Viewer

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)

<h2>Description of Detailed Steps</h2>

Section 1

Generating your Virtual Machine within Microsoft Azure

1. Create a text file or note pad to keep track of your information.
2. Create a Virtual Machine (You can create a Resource Group when creating your vm)
3. Create Virtual Machine in a country (try your country or a country close, so your vm isn’t too slow)
4. When creating vm before you are completely finished, got to networking. a. Find Nic (Network Security Group) then you will create your own firewall. b. Click advanced option create new. Remove the default rule them add your own.
       c. Destination port for the rule will be *. The priority will be 100. 

Section 2

Create Lot Analytics Workspace

5. When creating Law make sure to use same RG 
6. Head over to Microsoft Defender For Cloud to enable the abilty to gather logs 
      a. Enable in environment settings and disable SQL severs       b. Tap Data collection underneath defender plan where you enabled settings, then click All Events. 
7. Connect log analytics workspace to vm
      a. Click on your Law, below it will be an option that says vm       b. Click on the VM tab to connect your law to your VM

Setting up Microsoft Sentinel 

8. In Microsoft sentinel connect your law
9. Remote into VM’s public IP
10. In your VM go to the start menu and type in Event Viewer (you can see the failed attempts)
11. Turn off firewall used cmd “wf.msc” 
12. Download custom security log exporter https://github.com/joshmadakor1/Sentinel-Lab 

      a. Paste in Powershell ISE
      
      b. Click on the VM tab to connect your law to your VM
      
Sign up with https://ipgeolocation.io/ to get API to use for code. 
13. Add custom log to law 
14. Find logs from desktop and find logs from windows 
15. Open note pad to paste logs from Event Viewer on your actual desktop 
16. Then Use C:\ProgramData\failed_rdp.log to put in for collection path for custom log in law then press Enter 
17. Right click on random log to Exact RAW data

      a. Highlight latitude then save exactration of raw data
      
      b. Highlight longitude then save exactration of raw data (check longitude and latitude to ensure logs are correct. If they are off modify and highlight to train proper algorithm)
      
      c. Start breaking key names : username, state, destination source and saving exaction

Setting up Geo Map

18. In Microsoft Defender for cloud click on Workbooks 
19. Edit workbooks and add query 
20. Type command to find logs
       a. 
FAILED_RDP_WITH_GEO_CL | summarize event_count=count() by sourcehost_CF, latitude_CF, longitude_CF, country_CF, label_CF, destinationhost_CF
| where destinationhost_CF != "samplehost"
| where sourcehost_CF !=

19. Once you have your log you can now pin point with your geo map!



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



