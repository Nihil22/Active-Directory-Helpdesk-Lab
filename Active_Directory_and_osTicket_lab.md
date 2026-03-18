# Active Directory & Helpdesk Lab

## Overview
This lab is used to demonstrate an understanding of a enterprise helpdesk environement, Where I simulate setting up an AD domain for an organization, in which I choose the OKC Thunder. Creating players, staff, management, and coaches). In the organization I set up GPO and user accounts. I then moved to hosting a ticketing systems using Windows IIS and osticket, I then simulated a user request and resolved the ticket utilizing priviliages as a user in the IT department. 

## Environment
- Run on a Dell T430 running Proxmox on a indepenent Vlan (192.168.10.0/24)
<img width="849" height="866" alt="Screenshot 2026-03-17 195318" src="https://github.com/user-attachments/assets/3d04db1a-d6c9-4e3e-a0e5-a2b1a6bcc1b6" />

## Part 1 — Active Directory Setup
- Created the domain lab.local and connected win10 vm and second windows server VM
<img width="1485" height="684" alt="win10domain_connection" src="https://github.com/user-attachments/assets/17e4ee2f-e1a4-449d-b0b3-732ab2c2f222" />

- Created OU and groups as follow. OU: Coaches, Players, Managment, Staff with corresponding groups: grp_players, grp_managment, grp_coaches, grp_staff
<img width="1398" height="834" alt="OKC_Thunder_OU" src="https://github.com/user-attachments/assets/d1007646-f813-4a67-ba62-33facf560c85" />

- Utilized a powershell script to add users to the OU and groups
<img width="1304" height="808" alt="PWsh_script1" src="https://github.com/user-attachments/assets/adfc118b-70cf-4ce5-83e3-d4f121edb599" />
<img width="1340" height="700" alt="pwsh_script2" src="https://github.com/user-attachments/assets/64d97925-2db1-4390-abaf-be4a0db5ebb7" />
<img width="1106" height="579" alt="pwsh_proof" src="https://github.com/user-attachments/assets/28deb94d-e88d-493f-b6c1-a1496aef18a2" />
<img width="1286" height="806" alt="pwsh_players_proof" src="https://github.com/user-attachments/assets/479c520f-a72a-4519-a6c5-a2bf0bff2197" />

- The following OU after the Powershell script

- Coaches
<img width="1286" height="760" alt="Coaches_OU" src="https://github.com/user-attachments/assets/0d292427-2524-45aa-8fc7-0e0e67fd8325" />

- Managment
<img width="1337" height="818" alt="management_OU" src="https://github.com/user-attachments/assets/b243540b-30df-413b-bdb4-8c9d40647b38" />

- Staff
<img width="1303" height="799" alt="Staff_OU" src="https://github.com/user-attachments/assets/c9842089-7d75-4242-b2a0-4ca03e17bc2d" />

- Players
<img width="1286" height="806" alt="pwsh_players_proof" src="https://github.com/user-attachments/assets/2967974f-2440-484d-b69d-a2094bb0662b" />

- Created IT deptartment in where I utilize the gil user to conduct support.
<img width="1078" height="664" alt="IT_dept" src="https://github.com/user-attachments/assets/017161df-67a6-4602-a259-d60ae13e13d6" />


- Configured Group Policy Restricting access to control panel for users outside IT dept
<img width="1425" height="831" alt="GPO_restrict_Cpn" src="https://github.com/user-attachments/assets/e034eb3f-8ef6-4bf2-9b2c-a3f2e0f50148" />

- Configured Group Policy enforcing password security settings and focing new signon for then new users
<img width="1311" height="846" alt="GPO_passwd" src="https://github.com/user-attachments/assets/8c5cbd78-55ee-43d3-a30d-e3256e0b390b" />



## Part 2 — osTicket Deployment
- For my Web server I utilized Windows IIS in which Installed PHP and MySQL

- IIS installed
<img width="1471" height="672" alt="Screenshot 2026-03-17 210312" src="https://github.com/user-attachments/assets/a40d1141-1611-4322-a56f-4ee0e1c51cce" />

- MYsql user creation
<img width="985" height="316" alt="Screenshot 2026-03-16 172925" src="https://github.com/user-attachments/assets/ea118cd7-9b84-46a4-94dd-8b7f58360064" />


- OsTicket Install
<img width="1362" height="829" alt="Osticket_install" src="https://github.com/user-attachments/assets/78d9d65d-c873-414f-bd9c-e82acb81cc4f" />

- OsTicket requires agents (IT dept), orgnaizations (groups), Help topics(what does the person genrally need help with)and then users(clients).

- OsTicket agents
<img width="1281" height="864" alt="osticket_agents" src="https://github.com/user-attachments/assets/a4a3d0dd-54f3-44e2-b41c-7b0a93cfc759" />

- OsTicket organizations
<img width="1310" height="867" alt="orgs_osticket" src="https://github.com/user-attachments/assets/298e164d-5aae-43c0-bcfd-c4fb20248dd7" />

- Osticket Users
<img width="1291" height="859" alt="osTicket_Osticket" src="https://github.com/user-attachments/assets/be9fe7e1-d194-4204-8d23-2e40eaaecfc6" />

- Help Topics
<img width="1281" height="854" alt="Screenshot 2026-03-17 212140" src="https://github.com/user-attachments/assets/ed2f317b-7876-4218-ba54-801220d795f3" />

## Part 3 — Helpdesk Simulation
- For the simulation I login in as a user of the OKC organization(shai gilgeous Alexander), submit a ticket that creds were lost on osticket. Login in to osticket as an agent (gil) response to the request, and then resolve the ticket and verifiy user connectivity

- Login as the user (shai) 
<img width="1481" height="680" alt="sim_login" src="https://github.com/user-attachments/assets/445607c1-5828-4717-8737-35c7e12151bd" />

- connect to osticket from the user to send a ticket
<img width="1074" height="858" alt="osticket_portal_sim" src="https://github.com/user-attachments/assets/6f934c85-aeac-432b-bdff-8bd716cbbd5b" />

- Succesful ticket submission from user shai
<img width="1078" height="852" alt="Agent_acc_login" src="https://github.com/user-attachments/assets/dd349eac-e921-4c56-9286-d36bbfa29a3b" />

- Login from IT dept user and osticket agent account (gil)
<img width="1291" height="867" alt="Screenshot 2026-03-17 185912" src="https://github.com/user-attachments/assets/bcc7a544-f1e6-438d-bafe-503efa31e9f0" />
<img width="1293" height="872" alt="Screenshot 2026-03-17 184759" src="https://github.com/user-attachments/assets/405e257d-397b-4be3-a4f9-6297ff98e457" />

- Agent Gil recives the ticket from Shai regarding account lockout issues
<img width="1290" height="865" alt="sim_response_ticket" src="https://github.com/user-attachments/assets/a917bf5d-1e71-4dca-8d80-de4373eccfc0" />

- Responds to the ticket in Active Directory Users and Computers(ADUC) to reset password for user shai 
<img width="1261" height="862" alt="AD_reset_pswd" src="https://github.com/user-attachments/assets/1df5f572-af36-4e67-ac2a-821e7850f88d" />

- Resolves ticket with temp password for user.
<img width="1290" height="854" alt="resolved_ticket" src="https://github.com/user-attachments/assets/ab7379df-9afe-4377-a6cc-c0b8600a1091" />

- User shai logins in with Temp@12345 credentials
<img width="1481" height="680" alt="sim_login" src="https://github.com/user-attachments/assets/b7539a8c-1670-4226-96d1-fc1e1b25d52e" />

## Challenges & Troubleshooting
- I had issues with with the web server setup PHP and FastCGI I needed to install them seperatly aswell as the Visual C++ Redistributable.
- Also when installing osTicket Fastcgi and IIS had max_execution times which I needed to increase for it to install.
- Also had small issue with MySQL user creation
- Then Lastly when connecting the Win10 machine I turned off Control panel with GPO and couldn't access the domain server share as network share was off when trying to set desktop screen saver GPO


