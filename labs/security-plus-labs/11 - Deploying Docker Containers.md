# Lab: Deploying Docker Containers 

## Objective
In this lab, I created a distributed app that runs across five Docker containers and tested it.


## Steps taken
- Downloaded an example app from https://github.com/dockersamples/example-voting-app
- Built the Docker containers
- Opened a browser to https://localhost:5000  
- Opened another browser to https://localhost:5001    
- Examined the Docker container statistics and components

## Screenshots and observations
*Running PowerShell commands*
<img width="1106" height="611" alt="3 3 1 – Deploying Docker Containers 1 - running ps command" src="https://github.com/user-attachments/assets/b32e9efb-e2ab-4ba4-886c-a63311a63f3a" />

*Visiting localhost:8080 and voting 'dogs'*
<img width="1904" height="1018" alt="3 3 1 – Deploying Docker Containers 2 - visiting localhost 8080 and voting dogs" src="https://github.com/user-attachments/assets/ba6449d1-4c21-4717-8e4e-1cc93739bb15" />

*Visiting localhost:8081 to check results*
<img width="1904" height="1017" alt="3 3 1 – Deploying Docker Containers 3 - visiting localhost 8081 to check results" src="https://github.com/user-attachments/assets/d64ecc7a-9c69-414c-96a7-94cf71cfb53c" />

*Examining Docker*
<img width="1884" height="1010" alt="3 3 1 – Deploying Docker Containers 4 - examining docker" src="https://github.com/user-attachments/assets/feb3848e-29eb-48bb-9f6e-4f3ca2ddd3de" />

*Examining PowerShell after running the container*
<img width="1109" height="607" alt="3 3 1 – Deploying Docker Containers 5 - checking powershell" src="https://github.com/user-attachments/assets/0b1497db-dda2-4eb8-820c-2c606455403b" />

## Key takeaways
This lab showed me how easy it is to set up and deploy containers to run apps for testing.

## Relevance
Using containers allows developers to run and test applications, ensuring that the app has things like environment consistency and isolation before deploying to the real-world.
