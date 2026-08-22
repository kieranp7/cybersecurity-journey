# Lab: Performing a Buffer Overflow

## Objective
The point of this lab was to test and use Kali Linux Metasploit to perform a buffer overflow against Windows XP PRO. 

## Steps taken
- Verified both IP addresses of the Kali Linux and XP virtual machines
- Checked connections and users before implementing anything
- Used the exploit on Kali and established the connection
- Looked at Task Manager on XP to see the process running
- Performed a hashdump on Kali to get the password hashes of the users on XP
- Remotely created a new user and set them to administrator on the XP machine, via Kali
- Collected evidence that the tasks were successful

## Screenshots and observations
*Confirming connection between the machines*
<img width="1904" height="1024" alt="2 5 1 - Performing a Buffer Overflow 1 - Confirming connection via ping" src="https://github.com/user-attachments/assets/57358df7-e452-4cc6-b539-3e0e7bb6753e" />

*Checking connections and users on the target machine*
<img width="1909" height="1032" alt="2 5 1 - Performing a Buffer Overflow 2 - Checking Ports and Users on XP" src="https://github.com/user-attachments/assets/fc119c3d-7ecb-4f57-a05a-dac1a57433fc" />

*Running the exploit and establishing a connection*
<img width="1915" height="1028" alt="2 5 1 - Performing a Buffer Overflow 3 - Exloiting and establishing a connection" src="https://github.com/user-attachments/assets/24ddcc63-067b-4d00-bd4a-4c397d88d195" />

*Showing the Process ID running in Task Manager*
<img width="1912" height="1026" alt="2 5 1 - Performing a Buffer Overflow 4 - Showing PID in Task Manager" src="https://github.com/user-attachments/assets/b2d5019d-913d-4dc5-86a7-8918fd8745b8" />

*Performing a hashdump to get the password hashes*
<img width="1913" height="1028" alt="2 5 1 - Performing a Buffer Overflow 5 - Performing a Hashdump to get password hashes" src="https://github.com/user-attachments/assets/7c758a6d-92ae-4656-b4a6-a865199a2cc6" />

*Creating a new user and giving them admin permissions*
<img width="1918" height="1072" alt="2 5 1 - Performing a Buffer Overflow 6 - Creating new user and setting to admin" src="https://github.com/user-attachments/assets/a7885662-27d2-4fd5-9c8d-2e6682a9a20f" />

*Exiting the connection and showing it's gone*
<img width="1912" height="1028" alt="2 5 1 - Performing a Buffer Overflow 7 - Exiting the connection" src="https://github.com/user-attachments/assets/7dc25d1c-37b2-474d-9f91-6581c544a17e" />

*Showing the new account logged into the target machine*
<img width="1906" height="1027" alt="2 5 1 - Performing a Buffer Overflow 8 - Showing the new account logged in" src="https://github.com/user-attachments/assets/90821b07-7a72-4136-a7dd-6e6a35235730" />

## Key takeaways
During this lab, I learned how easy it was to get into a vulnerable machine with simple tools and start manipulating it, without anyone knowing it was happening. 

It was also almost impossible to tell by looking at the task manager and didn't produce any logs in the event viewer, which makes it even more dangerous.

## Relevance
This lab was relevant because it shows how easy it is to exploit vulnerable systems, without the victim knowing anything is going on. It also proves how easy it is to manipulate and steal information without being near the victim's PC.
