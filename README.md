# SIEM-Implementation-and-Analysis

## Objective

To set up a home lab for Elastic Stack Security Information and Event Management (SIEM) using Elastic Cloud and a Kali Linux VM, including generating and analyzing security events.


### Skills Learned

Installation and configuration of Elastic Stack and Kali Linux, log collection and forwarding, security event generation and analysis, dashboard creation, and alert setup in Elastic SIEM.

### Tools Used

- Elastic Cloud (Elasticsearch, Kibana, Elastic Agent) 
- VirtualBox
- Kali Linux VM

## Steps

- Create a free Elastic Cloud account and set up an Elastic instance.
- Install and set up a Kali Linux VM.
  
Integration of Elastic Agent on Kali host:
![Screenshot 3_28_2024 4_23_37 PM](https://github.com/fypm2000/SIEM-Implementation-and-Analysis/assets/117059426/d862717f-01a2-481e-8432-993ac0bb4068)
- - The command was used to install, enroll, and start the Elastic Agent on Kali VM to collect and forward logs.

![kali-linux-2024 1-virtualbox-amd64  Running  - Oracle VM VirtualBox 3_28_2024 4_23_49 PM](https://github.com/fypm2000/SIEM-Implementation-and-Analysis/assets/117059426/5a70dd08-0426-4227-a7e9-ff67ca54d6f3)
- The following command verifies that the agent has been installed correctly: sudo systemctl status elastic-agent.service

Generate security events using Nmap on the Kali VM.
![kali-linux-2024 1-virtualbox-amd64  Running  - Oracle VM VirtualBox 3_28_2024 4_34_27 PM](https://github.com/fypm2000/SIEM-Implementation-and-Analysis/assets/117059426/fd569489-f8d6-4d21-95a6-0c239fc89204)


Query and analyze logs in Elastic SIEM.
![Stream - Logs - Observability - Elastic - Personal - Microsoft​ Edge 3_28_2024 4_41_52 PM](https://github.com/fypm2000/SIEM-Implementation-and-Analysis/assets/117059426/6ffdd3da-8b2b-4047-a8cc-1b4309d1bd04)
- Filtered query logs by searching: event.action:“nmap”
- The details of the log show it originated from a Linux host, with the command sudo nmap 10.0.2.15 executed, indicating a use of elevated privileges to scan the network address.

![Stream - Logs - Observability - Elastic and 8 more pages - Personal - Microsoft​ Edge 3_29_2024 5_07_15 PM](https://github.com/fypm2000/SIEM-Implementation-and-Analysis/assets/117059426/6ba31e25-8f71-451a-b17d-99148a0b8818)
- The process is detailed with the arguments sudo nmap -A -T4 10.0.2.15, denoting an aggressive scan with OS detection, version detection, script scanning, and traceroute on the target IP address.


Create dashboards and alerts for monitoring security events.
![New Dashboard - Elastic and 1 more page - Personal - Microsoft​ Edge 3_28_2024 5_42_04 PM](https://github.com/fypm2000/SIEM-Implementation-and-Analysis/assets/117059426/df1855c3-a334-4846-83e6-6454ce8e7248)
![New Dashboard - Elastic and 1 more page - Personal - Microsoft​ Edge 3_28_2024 6_15_09 PM](https://github.com/fypm2000/SIEM-Implementation-and-Analysis/assets/117059426/a050934f-9208-42a9-989c-97dd2a65802d)
- Created a new rule in Elastic SIEM to alert on any occurrences of Nmap scans, with the action set to send an email notification when the rule is triggered.






