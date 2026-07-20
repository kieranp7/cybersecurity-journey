# Lab: Abusing Unsanitised Input

## Objective
In this lab, I will cause a vulnerable web app to execute an unauthorised command using Metasploitable2 and a standard web browser.

## Steps taken
- Verified the IP address of Metasploitable2 and pinged it to check that the connection is up
- Tested DVWA Command Execution in a browser
- Tested the double command on the Metasploitable2 command prompt
- Tested the double command at DVWA Command Execution to see what's outputted
- Examined the underlying vulnerable code to see why it was a problem

## Screenshots and observations
*Testing the DVWA Metasploitable2 site by pinging 8.8.8.8 to ensure it works*
<img width="945" height="541" alt="2 6 1 - Abusing Unsanitized Input 1 - Testing DVWA to make sure it works" src="https://github.com/user-attachments/assets/bd875276-bb3a-4e96-a9c4-763e62bff909" />

*Testing the double command on DVWA command execution*
<img width="929" height="954" alt="2 6 1 - Abusing Unsanitized Input 2 - Testing double command on DVWA command execution" src="https://github.com/user-attachments/assets/5cdab9f2-a0b1-4088-8a00-21da519cfcf9" />

*Examining the vulnerable code on DVWA*
<img width="929" height="776" alt="2 6 1 - Abusing Unsanitized Input 3 - Examing vulnerable code" src="https://github.com/user-attachments/assets/33485ac6-0ab7-4ccf-b319-2accf6e1301c" />

## Key takeaways
This taught me how something simple could be exploited, such as when a developer forgets or doesn't know to implement controls to prevent malicious code from being executed inside input fields.

## Relevance
In the real world, it's very easy for a developer to forget to add in basic controls to prevent hacking, and this lab shows how dangerous it can be.
