# Lab: Crashing a Target with DoS 

## Objective
In this lab, I performed a Slowloris denial-of-service attack on Kali Linux against Metasploitable2. I then used Wireshark and a browser to analyse the attack mechanism and observe its effect. 


## Steps taken
- Launched and started Wireshark
- Downloaded and installed Slowloris on Kali
- Ensured that netspeed2.sh is allowed to run as a program
- Started netspeed2.sh to monitor Kali Linux traffic
- Switched to Metasploitable2 (SSH in via PuTTY as the pipe symbol wouldn't work on Metasploitable) to find out the Process ID of apache2
- Used the ps and top commands to start monitoring the CPU and RAM utilisation of apache2
- Verified normal traffic utilisation on Kali
- Launched the slowloris DoS attack
- Examined the attack artefacts

## Screenshots and observations
*Downloaded and installed Slowloris on Kali*
<img width="948" height="551" alt="2 15 1 – Crashing a Target with DoS 1 - get slowloris" src="https://github.com/user-attachments/assets/3c329d3b-0225-48e9-890d-f18988a4e53d" />

*Running the netspeed2.sh script*
<img width="954" height="635" alt="2 15 1 – Crashing a Target with DoS 2 - running netspeed sh" src="https://github.com/user-attachments/assets/2b25878c-b5c1-4c08-aba9-a7d41c69890a" />

*Monitoring the CPU and RAM usage of apache2*
<img width="1913" height="1022" alt="2 15 1 – Crashing a Target with DoS 3 - monitoring CPU and RAM" src="https://github.com/user-attachments/assets/a87bfd62-3528-4219-8d46-5bbbfbb7e1a7" />

*Launching the DoS attack on Kali*
<img width="1910" height="1028" alt="2 15 1 – Crashing a Target with DoS 4 - launching dos attack" src="https://github.com/user-attachments/assets/e815c90c-9104-448d-9ab3-9d5097d24342" />

*Stopping the attack and examining the results in Wireshark*
<img width="1906" height="1027" alt="2 15 1 – Crashing a Target with DoS 5 - stopping attack and examining" src="https://github.com/user-attachments/assets/481819d6-b315-4f53-9002-6717ebe742a1" />

## Key takeaways
This lab showed me how easy it is to run a DoS attack and stop real users from accessing a website.

## Relevance
DoS attacks are another common type of attack that occurs regularly, so it's important to understand how they work to try and defend against them.
