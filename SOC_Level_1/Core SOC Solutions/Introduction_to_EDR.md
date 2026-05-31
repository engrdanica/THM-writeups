### Room Overview

a. Room Name: Investigate an Alert on EDR

b. Difficulty: Easy

c. Tools Covered: Endpoint Security

### Objectives
- Perform triage on each detection using the available information on the given site in TryHackMe
- Understand the visibility of the detection in EDR

### Thoughts/Completion Process

#### Given Dashboard

<img width="1076" height="821" alt="image" src="https://github.com/user-attachments/assets/a38b203c-4598-4a1c-9e8c-3f12f3d4fbbd" />


##### Q1. Which tool was launched by CMD.exe to download the payload on DESKTOP-HR01?
When I entered the site, it was really direct about what to see and navigate. Curiosity just hit me, and try to click the buttons and familiarize myself with the console.
- Click **DESKTOP-HR01** to view the details needed for the lab, then go to Process Info.
<img width="1017" height="712" alt="image" src="https://github.com/user-attachments/assets/2c8cc2cf-bc1e-431a-8edf-74462719b148" />
- You can see the process chain, thus leading to seeing what tool was launched by CMD.exe, which is **cURL.EXE**

##### Q2. What is the absolute path to the downloaded malware on the DESKTOP-HR01 machine?
I wasn't sure what an absolute file path is, so I had to look it up. Since it's the very beginning of the file system, I looked for the series of steps on what was happening on that detection.
- Click on the **IOC/Indicators** tab; you can see the "source" and "file path".
<img width="1021" height="568" alt="image" src="https://github.com/user-attachments/assets/66e2e205-aaea-4ca1-87f0-e7c91f73d8f2" />
- Answer: C:\Users\Public\install.exe

##### Q3. What is the absolute path to the suspicious syncsvc.exe on the WIN-ENG-LAPTOP03 machine?
Same as Q2, but you have to file the absolute path on the host **WIN-ENG-LAPTOP03** machine
<img width="1083" height="585" alt="image" src="https://github.com/user-attachments/assets/8cc5409c-0824-40ca-abbe-a8fd64f721d9" />
- Answer: C:\Users\haris.khan\AppData\Local\Temp\syncsvc.exe

##### Q4. On which URL was the exfiltration attempt being made on WIN-ENG-LAPTOP03?
This was a bit tricky, but as a SOC Analyst, you have to be keen with the details. So since the suspicious tool was syncsvc.exe, I went back to **Process Info** and clicked on **syncsvc.exe**.
<img width="1017" height="873" alt="image" src="https://github.com/user-attachments/assets/4d493ae7-691e-4a32-afa1-62bf4051ace7" />
- Answer: https://files-wetransfer.com/upload/session/ab12cd34ef56/dump_2025.dmp

##### Q5. What was UpdateAgent.exe labelled by Threat Intel on DESKTOP-DEV01?
On the Dashboard, click on **WIN-ENG-LAPTOP03**. As seen in Q4, you have noticed that there's also a **Threat Intel** under the **Process Info** tab
<img width="1057" height="784" alt="image" src="https://github.com/user-attachments/assets/d515968d-76b3-44cc-9337-19e5efaa2b46" />
- Answer: Known internal IT utility tool

### Takeaways
| Terms/Command | Description |
|----|----|
| Absolute Path | Complete address of a file or directory in a computer system |
|IOC/Indicators | Piece of digital forensics that suggests that an endpoint or network may have been breached |

### Final Thoughts/Learnings
As a SOC Analyst, you really have to know what the terms are and be detail-oriented. You also have to explore the console of the EDR Tool that you'll be using; you have to familiarize yourself because every minute counts in alert triaging.
