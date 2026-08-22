# Lab: O.MG No Cable

## Objective
The objective of this lab was to attempt to use a malicious batch file to replace the functionality of the O.MG charging cable when hacking a computer.

## Steps taken
- Disabled antivirus and real-time protection so I could run the script
- Temporarily changed my execution policy to RemoteSigned *(Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned -Force)*
- Loaded up Metasploitable and obtained the IP address
- Ran *sudo chmod -R 777 /var/www/* inside Metasploitable to allow uploads
- Edited an activity file called hashdump.ps1.txt to include Metasploitable's IP address
- Edited an activity file called omg.bat.txt to include the same IP address, and copied it to a batch file
- Used FileZilla to upload the hashdump script to Metasploitable via FTP
- Ran the exploit (omg.bat) from my host PC

## Screenshots and observations
*Getting the IP address and allowing file transfers*
<img width="725" height="450" alt="2 2 2 - O MG No Cable - Setting up Metasploitable" src="https://github.com/user-attachments/assets/555118d8-1189-4241-845a-8873e163b237" />

*Editing the hashdump file*
<img width="966" height="555" alt="2 2 2 - O MG No Cable - Setting up Hashdump file" src="https://github.com/user-attachments/assets/3a0543fc-e64a-4dc6-bcbc-fe6b8b4a313f" />

*Editing the omg file*
<img width="953" height="580" alt="2 2 2 - O MG No Cable - Setting up O MG Bat File" src="https://github.com/user-attachments/assets/9f51ba08-42a7-46f7-a17a-5aea47cdc27c" />

*Converting the omg.bat.txt to a .bat file*
<img width="693" height="53" alt="2 2 2 - O MG No Cable - Converting to bat file" src="https://github.com/user-attachments/assets/234a6c82-9be8-4f61-b039-4a94a79db3a3" />

*Connecting with FileZilla via FTP and uploading the hashdump file to Metasploitable*
<img width="1169" height="521" alt="2 2 2 - O MG No Cable - Connected via FTP and adding PS script" src="https://github.com/user-attachments/assets/751891e2-5c8d-47f3-889c-ce96f21faa50" />

*Running the exploit*
<img width="968" height="293" alt="2 2 2 - O MG No Cable - Executing script remotely" src="https://github.com/user-attachments/assets/9ee0daa9-57a0-4bbd-b071-947f3bd0467f" />

*Hash file created and viewable via FileZilla*
<img width="1172" height="762" alt="2 2 2 - O MG No Cable - Creating and Saving Hashes" src="https://github.com/user-attachments/assets/ff98d5c5-f84a-4c27-b323-32de238070d1" />

*Viewing the hash file that was created*
<img width="960" height="580" alt="2 2 2 - O MG No Cable - Hash file created" src="https://github.com/user-attachments/assets/a3f0b86b-53ba-4eb1-bcad-8371398941e9" />

## Key takeaways
This lab taught me how easy it can be to get into another system and remotely execute malicious content, as well as mess with the victim's PC and gather their information

Unfortunately, I couldn't get the hashes into my hash file due to permissions/restrictions on my host PC, and couldn't figure out how to get around it, but everything else worked up until this point, so the theory works.

## Relevance
In the real world of credential harvesting and data exfiltration, attackers can operate in a similar way by escalating privileges to extract system hashes and move them to a remote server. Making it easy for attackers to spend as much time as they want looking through the information and  doing further malicious things with it.
