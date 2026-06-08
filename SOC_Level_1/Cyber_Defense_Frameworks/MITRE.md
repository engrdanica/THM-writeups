### Room Overview

a. Room Name: MITRE

b. Difficulty: Medium

c. Tools Covered: MITRE ATT&CK, CAR Knowledge Base, D3FEND, MITRE Engage™, and other relevant tools

### Objectives
- Understand the purpose and structure of the MITRE ATT&CK® Framework
- Explore how security professionals apply ATT&CK in their work
- Use cyber threat intelligence (CTI) and the ATT&CK Matrix to profile threats
- Discover MITRE’s other frameworks, including CAR and D3FEND

### Thoughts/Completion Process

#### ATT&CK Framework

##### Q1. What Tactic does the Hide Artifacts technique belong to in the ATT&CK Matrix?
So what I did was go to the website https://attack.mitre.org/matrices/enterprise/, then just searched for the words "Hide Artifacts"

<img width="956" height="908" alt="image" src="https://github.com/user-attachments/assets/cddc6e1a-0d1e-40c0-ba27-72dddc307209" />

##### Q2. Which ID is associated with the Create Account technique?
Same as what I did for the first question: just search it and hover the mouse over it, and you'll get the ID
<img width="957" height="909" alt="image" src="https://github.com/user-attachments/assets/8b370f22-5275-4bca-a795-c4e590c18237" />

#### ATT&CK in Operation

##### Q1. In which country is Mustang Panda based?
THM already provided the link for Mustang Panda (https://attack.mitre.org/groups/G0129/)
Upon checking the description, it already said that it originates from **China**

<img width="958" height="906" alt="image" src="https://github.com/user-attachments/assets/1ffdc8b2-2e20-460a-a997-41db4fd899af" />

##### Q2. Which ATT&CK technique ID maps to Mustang Panda’s Reconnaissance tactics?
Since reconnaissance is about gathering information, I've searched for "Information" as the keyword. Mustang Panda is known for phishing as well; from the T1598 description, it used web bugs to profile the intended users.

<img width="956" height="906" alt="image" src="https://github.com/user-attachments/assets/85f3fa6b-fcfd-42e9-9b9a-0ecb0539dfff" />

##### Q3. Which software is Mustang Panda known to use for Access Token Manipulation?
I used the words "Access Token Manipulation" and immediately saw **Cobalt Strike** for its Access Token Manipulation

<img width="961" height="906" alt="image" src="https://github.com/user-attachments/assets/be3a9968-2653-44c0-bec7-3d68de688de2" />

#### ATT&CK for Threat Intelligence

Given Link: https://attack.mitre.org/groups/

##### Q1. Which APT group has targeted the aviation sector and has been active since at least 2013?
Again, I am utilizing Ctrl+F for the keywords given in the question. I searched for "aviation" and the first entry was **APT33**, which has also been active since at least 2013.

<img width="957" height="907" alt="image" src="https://github.com/user-attachments/assets/49b6c5d6-f44c-410b-8b45-f3092232fe7f" />

##### Q2. Which ATT&CK sub-technique used by this group is a key area of concern for companies using Office 365?
This was a bit tricky, so by using the keyword "Office 365", you'll be directed to Scattered Spider. Upon checking the group, it says that it has expanded into hybrid cloud.

<img width="959" height="906" alt="image" src="https://github.com/user-attachments/assets/bbcbd7b7-813a-4f76-b9eb-9549f9354204" />

Then you scroll down to see the techniques, and you can see there the Cloud Account for Account Discovery, which really makes sense for Office 365 since it is a cloud-based subscription.

<img width="954" height="906" alt="image" src="https://github.com/user-attachments/assets/49beacbc-b851-4a78-8808-4be4de8199cf" />

##### Q3. According to ATT&CK, what tool is linked to the APT group and the sub-technique you identified?
So we have APT33 in Q1 and Cloud Account for Q2. So I went to the APT group and searched for "Cloud Account", which returned **Ruler**.

<img width="956" height="905" alt="image" src="https://github.com/user-attachments/assets/116e8bad-aec3-44aa-9767-6f5a759846a4" />

##### Q4. Which mitigation strategy advises removing inactive or unused accounts to reduce exposure to this sub-technique?
I went to the "Cloud Account" link (https://attack.mitre.org/techniques/T1078/004/) because it pertained to the sub-technique. Then I searched "remove" and it showed the answer **User Account Management**

<img width="958" height="907" alt="image" src="https://github.com/user-attachments/assets/f01c003f-98c6-4427-a606-9160b7d5a64a" />

##### Q5. What Detection Strategy ID would you implement to detect abused or compromised cloud accounts?
Using the keyword "Abused", I immediately found the answer under the Detection Strategy.

<img width="905" height="477" alt="image" src="https://github.com/user-attachments/assets/bf8b55d5-f3cc-4112-b410-669a65076c5b" />

#### Cyber Analytics Repository (CAR)

##### Q1. Which ATT&CK Tactic is associated with CAR-2019-07-001?

I checked the link, and it shows Tactic **Defense Evasion**. 

<img width="954" height="723" alt="image" src="https://github.com/user-attachments/assets/544e4845-1403-4290-8bcc-43636959539d" />

##### Q2. What is the Analytic Type for Access Permission Modification?
The answers are actually straightforward once you've scanned the website. The answer is "Situational Awareness"

<img width="956" height="907" alt="image" src="https://github.com/user-attachments/assets/56c07a56-aa89-4175-9e89-4e0bb9a2de4b" />

#### Cyber Analytics Repository (CAR)

##### Q1. Which sub-technique of User Behavior Analysis (opens in new tab) would you use to analyze the geolocation data of user logon attempts?
I was scanning the website at first without searching for the keyword, but I spotted the answer because the description is also direct to the point.

<img width="960" height="908" alt="image" src="https://github.com/user-attachments/assets/9e7b1616-5a80-4d50-8cc1-18c8992507f2" />

##### Q2. Which digital artifact does this sub-technique rely on analyzing?
I went ahead and clicked the User Geological Logon Pattern Analysis, which led me to its deeper information. The information was straightforward, and there's also a diagram that shows what it analyzes.

<img width="1563" height="811" alt="image" src="https://github.com/user-attachments/assets/b811f24f-0283-4f3a-8fe4-23f956d77367" />

#### Other MITRE Projects

##### Q1. What technique ID is associated with Scrape Blockchain Data in the AADAPT framework?
Same as the other links; it's just simple common sense that you just have to find which ID, or even just the keyword.

<img width="958" height="803" alt="image" src="https://github.com/user-attachments/assets/89f16c8e-83a8-4595-9ec6-4caa51c99ec2" />

##### Q2. Which tactic does LLM Prompt Obfuscation belong to in the ATLAS framework?
When the site loads, you can definitely see the answer immediately, as the website is very straightforward

<img width="958" height="796" alt="image" src="https://github.com/user-attachments/assets/da07366e-54e4-4cbb-b399-05870dd3970d" />

### Takeaways
| Terms/Command | Description |
|----|----|
|  MITRE ATT&CK Matrix | A powerful visual representation of all tactics and techniques that exist within the framework |
|Tactic| An adversary's goal or objective. The “why” of an attack |
|Technique | How an adversary achieves their goal or objective |
|Procedure | The implementation or how the technique is executed |
| Cyber Analytics Repository | A knowledge base of analytics developed by MITRE based on the MITRE ATT&CK adversary model|
| D3FEND | structured framework that maps out defensive techniques and establishes a common language for describing how security controls work|

### Final Thoughts/Learnings
To be honest, I have already gone through MITRE ATT&CK at work bootcamp that gave me full fundamentals, and it was really just full-on understanding and common sense. I also had the techniques lessons in Google SecOps work since we also deal with the queries. Overall, this lesson gave me deeper knowledge of MITRE; I could've labelled it as easy, as it is very straightforward. 
