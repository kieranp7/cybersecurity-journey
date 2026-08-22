# Lab: Recognising Directory Traversal 

## Objective
In this lab, I performed a directory traversal attack and then examined its artefacts. 

## Steps taken
- Opened a browser to DVWA and examined URL paths
- Used command injection to discover/verify the Metasploitable internal path
- Used a PHP File Inclusion vulnerability to perform directory traversal
- Verified that the directory traversal was logged by Apache2
- Used PuTTY on the Host PC to SSH to Metasploitable
- Used PuTTY to capture the Apache2 log output
- Examined the captured log file for directory traversal artefacts

## Screenshots and observations
*Performing Directory Traversal*
<img width="962" height="662" alt="2 13 1 - Recognising Directory Traversal 1 - performing directory traversal" src="https://github.com/user-attachments/assets/9b72596d-13d0-4779-9627-fd9709937401" />

*Using PuTTY to SSH into Metasploitable*
<img width="1730" height="988" alt="2 13 1 - Recognising Directory Traversal 2 - using putty to SSH into metasploitable" src="https://github.com/user-attachments/assets/e91e0cc4-0b4d-4d48-a1fd-5b0d4d628251" />

*Capturing Apache2 log output*
<img width="1748" height="961" alt="2 13 1 - Recognising Directory Traversal 3 - capturing apache2 log output" src="https://github.com/user-attachments/assets/3e8de050-330e-422e-9460-d24b256b132f" />

*Examining the log file*
<img width="1890" height="1021" alt="2 13 1 - Recognising Directory Traversal 3 - examining the log file" src="https://github.com/user-attachments/assets/31a61e5a-1abe-4b98-95b4-0e5f1bc322c1" />

## Key takeaways
This lab showed me how easy it is to hop through a web server's directory with simple commands to get to hidden data that shouldn't be available to the outside world.

## Relevance
This vulnerability allows attackers to bypass security controls and cause damage, and usually comes from improper input validation.
