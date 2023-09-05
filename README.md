<p align="center">
<img src="https://i.imgur.com/R5OzmdT.png" height="55%" width="55%" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Microsoft Azure - Active Directory (AD)</h1>

This demonstration outlines sharing out resources over the network, and creating file shares to allow Read, Write, or Deny access to individual users or groups

<i><b>*Note</b> this is a continuation of the Previous Lab: <a href="https://github.com/abelbelay/configure-ad">Configuring Active Directory within Azure Virtual Machines</a></i>

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services

  <h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>
<li>Create some sample file shares with various permissions
<li> Attempt to access file shares as a normal user
<li>Create a Security Group, assign permissions, and test access
</li>

<h2>Step Process</h2>

<h3>Log into your virtual Machines</h3>
Conncect/log into"DC-1" as your domain admin account(mydomain.com\abel_admin)
<img src="https://user-images.githubusercontent.com/142059616/265548916-829aff32-15cc-484c-b6b6-7780f6ba5456.png">
Connect/log into "Client-1" as a normal user (mydomain.com\*someuser*)
<img src="https://user-images.githubusercontent.com/142059616/265549139-bf50bbc6-da1d-40ca-968b-c9fb52ae690a.png">

<h4>We will create 4 folders in our C:\ drive. "read-access", "write access", "no-access", "accounting"</h4>
<img src="https://user-images.githubusercontent.com/142059616/265550559-c45b9430-caf9-4253-8c7a-c6d657bcfcd3.png">


<h4>We will now set permissions for these "Domain Users" with the new folders we have created</h4>
<li>Folder:Read Access-->Group:Domain Users-->Permission:Read</li>
<li>Folder:Write Access-->Group:Domain Users-->Permission:Read/Write</li>
<li>Folder:No Access-->Group:Domain Admins-->Permission:Read/Write</li>
<p align="center">
<img src="https://user-images.githubusercontent.com/142059616/265551161-2d63b441-937c-4382-b2a8-0ab6cfceb084.png" height="50%" width="48%">
<img src="https://user-images.githubusercontent.com/142059616/265551329-dd3b193c-057b-4cf0-b3e6-0b0325b573d2.png" height="50%" width="48%">
<img src="https://user-images.githubusercontent.com/142059616/265551520-b24ebd1e-ae58-4539-92f7-972712e6291b.png" height="50%" width="48%">
</p>

<h4>We are going to open the "Client-1" VM and navigate the shared folders</h4>
<p align="center">
<img src="https://user-images.githubusercontent.com/142059616/265553501-861256c7-1243-4ca7-9b85-977cd9ccf633.png" height="76%" width="70%"></p>
In this example we can see that since we didn't give permission for the domain user to access the "no access" folder, they're not permitted from accessing it.
<p align="center"><img src="https://user-images.githubusercontent.com/142059616/265553899-3cbbb4e8-6352-487a-b84e-da518c7b82cd.png" height="76%" width="70%"></p>
We will go back to the Dc-1 server and create a text file in the "read access" folder to test out our theory further. You can name the txt file whatever you'd like
<p align="center">
<img src="https://user-images.githubusercontent.com/142059616/265554671-80acd228-4ff1-4979-a432-a25f57ec8635.png" height="66%" width="60%"></p>
Now we will go back to "Client-1"
<img src="<img src="https://user-images.githubusercontent.com/142059616/265554671-80acd228-4ff1-4979-a432-a25f57ec8635.png" height="66%" width="60%">




