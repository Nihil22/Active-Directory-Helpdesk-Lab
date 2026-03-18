# Active Directory & Helpdesk Lab

## Overview
Brief description of what the project is and what technologies were used
This lab is used to demonstrate an understanding of a enterprise helpdesk environement, Where I simulate setting up an AD domain for an organization, in which I choose the OKC Thunder. Creating players, staff, management, and coaches). In the organization I set up GPO and user accounts. I then moved to hosting a ticketing systems using Windows IIS and osticket, I then simulated a user request and resolved the ticket utilizing priviliages as a user in the IT department. 
## Environment
- Run on a Dell T430 running Proxmox on a indepenent Vlan (192.168.10.0/24)
<img width="849" height="866" alt="Screenshot 2026-03-17 195318" src="https://github.com/user-attachments/assets/3d04db1a-d6c9-4e3e-a0e5-a2b1a6bcc1b6" />

## Part 1 — Active Directory Setup

- created the domain lab.local and connected win10 vm and second windows server VM
- <img width="1485" height="684" alt="win10domain_connection" src="https://github.com/user-attachments/assets/17e4ee2f-e1a4-449d-b0b3-732ab2c2f222" />
- created OU and groups as follow. OU: Coaches, Players, Managment, Staff with corresponding groups: grp_players, grp_managment, grp_coaches, grp_staff
- <img width="1398" height="834" alt="OKC_Thunder_OU" src="https://github.com/user-attachments/assets/d1007646-f813-4a67-ba62-33facf560c85" />
- Utilized a powershell to add users to the OU and groups
- <img width="1304" height="808" alt="PWsh_script1" src="https://github.com/user-attachments/assets/adfc118b-70cf-4ce5-83e3-d4f121edb599" />
-<img width="1340" height="700" alt="pwsh_script2" src="https://github.com/user-attachments/assets/64d97925-2db1-4390-abaf-be4a0db5ebb7" />
-<img width="1106" height="579" alt="pwsh_proof" src="https://github.com/user-attachments/assets/28deb94d-e88d-493f-b6c1-a1496aef18a2" />
-<img width="1286" height="806" alt="pwsh_players_proof" src="https://github.com/user-attachments/assets/479c520f-a72a-4519-a6c5-a2bf0bff2197" />
THe following OU after the Powershell script
-Coaches
-<img width="1286" height="760" alt="Coaches_OU" src="https://github.com/user-attachments/assets/0d292427-2524-45aa-8fc7-0e0e67fd8325" />

-Managment
-<img width="1337" height="818" alt="management_OU" src="https://github.com/user-attachments/assets/b243540b-30df-413b-bdb4-8c9d40647b38" />

-Staff
-<img width="1303" height="799" alt="Staff_OU" src="https://github.com/user-attachments/assets/c9842089-7d75-4242-b2a0-4ca03e17bc2d" />

-Players
-<img width="1286" height="806" alt="pwsh_players_proof" src="https://github.com/user-attachments/assets/2967974f-2440-484d-b69d-a2094bb0662b" />

-Also created IT deptartment in where I utilize the gil user to conduct support.
-<img width="1078" height="664" alt="IT_dept" src="https://github.com/user-attachments/assets/017161df-67a6-4602-a259-d60ae13e13d6" />


- Configured Group Policy Restricting access to control panel for users outside IT dept
- <img width="1425" height="831" alt="GPO_restrict_Cpn" src="https://github.com/user-attachments/assets/e034eb3f-8ef6-4bf2-9b2c-a3f2e0f50148" />
- Configured Group Policy enforcing password security settings and focing new signon for then new users
- <img width="1311" height="846" alt="GPO_passwd" src="https://github.com/user-attachments/assets/8c5cbd78-55ee-43d3-a30d-e3256e0b390b" />



## Part 2 — osTicket Deployment
- For my Web server I utilized Windows IIS in which Installed PHP and MySQL
- IIS installed
- <img width="1471" height="672" alt="Screenshot 2026-03-17 210312" src="https://github.com/user-attachments/assets/a40d1141-1611-4322-a56f-4ee0e1c51cce" />
- MYsql user creation
- <img width="985" height="518" alt="my_sql_install_user_created" src="https://github.com/user-attachments/assets/01828432-dcf4-47d8-90f5-ae0960c5b4e2" />
-OsTicket Install
-<img width="1362" height="829" alt="Osticket_install" src="https://github.com/user-attachments/assets/78d9d65d-c873-414f-bd9c-e82acb81cc4f" />
-osTicket requires agents (IT dept), orgnaizations (groups), Help topics(what does the person genrally need help with)and then users(clients).
- osTicket agents
<img width="1281" height="864" alt="osticket_agents" src="https://github.com/user-attachments/assets/a4a3d0dd-54f3-44e2-b41c-7b0a93cfc759" />
-OsTicket organizations
<img width="1310" height="867" alt="orgs_osticket" src="https://github.com/user-attachments/assets/298e164d-5aae-43c0-bcfd-c4fb20248dd7" />
-Osticket Users
<img width="1291" height="859" alt="osTicket_Osticket" src="https://github.com/user-attachments/assets/be9fe7e1-d194-4204-8d23-2e40eaaecfc6" />




- Once

## Part 3 — Helpdesk Simulation
- Screenshots of ticket submission from Win 10
- Agent resolving ticket
- Password reset workflow in AD

## Challenges & Troubleshooting
- Issues you hit and how you fixed them

