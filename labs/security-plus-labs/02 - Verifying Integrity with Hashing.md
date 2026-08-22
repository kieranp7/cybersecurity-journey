# Lab: Verifying Integrity with Hashing

## Objective
The objective for this lab session was to find out more about hashing, and how to check the integrity of a hash to ensure the file hasn't been altered.

## Steps taken
- Downloaded an XP ISO from https://archive.org/details/xp_pro_w_sp2_slipstreamed
- Checked the original hash (displayed on the website) against the downloaded file in Powershell
- Checked the original hash on Kali Linux terminal
- Checked the hash according to other algorithms to see the output

## Screenshots and observations

<img width="1871" height="736" alt="1 8 1 - Verifying Integrity with Hashing 1 - Checking Original Hash" src="https://github.com/user-attachments/assets/b5c8337c-987e-45a5-b539-b8424092917d" />

*This screenshot shows the process of checking the SHA1 hash in powershell against the original hash.*

<img width="1001" height="587" alt="1 8 1 - Verifying Integrity with Hashing 1 - Checking Original Hash Kali" src="https://github.com/user-attachments/assets/90762167-1651-4321-b57a-be73cfa38d53" />

*Checking the hash of the same file in Kali Linux*

<img width="1005" height="695" alt="1 8 1 - Verifying Integrity with Hashing 1 - Checking Other Hashes" src="https://github.com/user-attachments/assets/380b1261-d608-4858-a776-cd6fbfbe2bff" />

*Checking the hash for other algorithms as an exercise (MD5 & SHA256)*

## Key takeaways
I learned how to check the integrity of a file by checking the hash, using Powershell and Kali.

## Relevance
In the real world, checking the integrity of a file (such as checking the hash) is essential to ensure that the file you have is the original version, that hasn't been tampered with..
