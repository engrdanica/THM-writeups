# Room Overview

a. Room Name: Phishing Analysis Tools

b. Difficulty: Easy

c. Tools Covered: Email Analysis & ANYRUN

### Objectives
- Investigate phishing cases to apply your understanding and strengthen your analysis skills

### Thoughts/Completion Process

#### Your Account is on Hold

##### Q1. What reputable brand is this email tailored to impersonate?
I started the lab machine and loaded the Phish3Case1.eml. I've checked the email; you'll see directly how you will find the reputable brand, aka. Netflix.

<img width="1077" height="879" alt="image" src="https://github.com/user-attachments/assets/d18aa782-3f18-48be-af9f-832f61a1a90c" />

##### Q2. Based on the email headers, who is the intended recipient of this message?
Reading the email headers, I've found that the recipient is **redacted@yahoo.com**

<img width="1074" height="709" alt="image" src="https://github.com/user-attachments/assets/758e2909-a799-43ce-a94b-d73058253cc7" />

##### Q3. In Thunderbird mail, use View → Message Source. What is the Received: from IP address?
Checking the message source using Ctrl+U, it will show the IP address where it was received.

<img width="1074" height="850" alt="image" src="https://github.com/user-attachments/assets/e34d4e36-b863-4282-aa55-d9f66314bcc4" />


##### Q4. Check out the Return-Path field in the message source. What would you consider a domain of interest based on this field?
In the message source, you will see the domain directly in the Return-Path field. Which the answer is **etekno.xyz**.

<img width="1076" height="877" alt="image" src="https://github.com/user-attachments/assets/5d3bd7aa-1f98-4552-976a-07e4deb8996e" />

##### Q5. Investigate the UPDATE ACCOUNT NOW button. What is the shortened URL?
I hovered over the UPDATE ACCOUNT NOW button, then right-clicked and chose "Copy link location." It will show the shortened URL, which is **https://t.co/yuxfZm8KPg?amp=1**

<img width="1071" height="707" alt="image" src="https://github.com/user-attachments/assets/90dd6b08-f530-4b0a-96cb-be1d6a614e86" />


#### Update Payment Details

Given website: https://app.any.run/tasks/8bfd4c58-ec0d-4371-bfeb-52a334b69f59

##### Q1. How does ANYRUN classify this suspected phishing email?
I am not familiar with ANYRUN, so I've tried exploring more on the website, trying to figure out the classification. I saw in the upper right that it was the classification needed for this phishing analysis.

<img width="1912" height="909" alt="image" src="https://github.com/user-attachments/assets/e351feda-e5e7-4019-97c3-147d6c26a93b" />


##### Q2. What is the name of the PDF attachment?

From the analysis, the PDF attachment is payment-updateid.pdf.

<img width="1919" height="907" alt="image" src="https://github.com/user-attachments/assets/6994bf2b-1390-4845-be82-4105b8986f1e" />

##### Q3. Investigate the email attachment. What is the SHA256 hash of the PDF file?

Once clicking the Payment-updateid.pdf link...

<img width="1913" height="906" alt="image" src="https://github.com/user-attachments/assets/5f817edc-9691-498b-b954-64aad213a614" />

You will see more info on the PDF, including the SHA256 hash of the PDF file.

<img width="1919" height="907" alt="image" src="https://github.com/user-attachments/assets/1f3810ae-709e-4b08-b1d6-08720ac96a38" />

##### Q4. Check out the ANYRUN text report on the phishing email. Which IP address associated with the process AcroRd32.exe is flagged as malicious?

I had a hard time checking where to get the text report. So I found out that you click reports

<img width="1915" height="907" alt="image" src="https://github.com/user-attachments/assets/825e39c1-0048-48ce-b1b7-5e4ecf9710f5" />

Then click "Text Report". 

<img width="1914" height="898" alt="image" src="https://github.com/user-attachments/assets/d227be98-6584-43d2-8cc7-d1f0dd4398fb" />

Then I found the IP address associated with the IP that is malicious

<img width="1919" height="905" alt="image" src="https://github.com/user-attachments/assets/9ea8f7a0-c2a8-4a06-8c93-1ad5c7c4d57d" />

##### Q5. Continue investigating the text report. Which Windows process is classed as Potentially Bad Traffic?

Lastly, I searched for "Potentially Bad Traffic" in the report, and "svchost.exe" was the answer.

<img width="1919" height="907" alt="image" src="https://github.com/user-attachments/assets/111164eb-c354-46ee-a7ba-cafc44c336d8" />


#### Excel Executable

Given website: https://app.any.run/tasks/82d8adc9-38a0-4f0e-a160-48a5e09a6e83

##### Q1. How does ANYRUN classify the .xlsx attachment?

In the upper right side corner, ANYRUN classified the excel file as **Malicious Activity**

<img width="424" height="425" alt="image" src="https://github.com/user-attachments/assets/cf4c01dd-d145-4e9d-ba1d-10363babdf15" />

##### Q2. What is the file name of the Excel attachment?

The upper right of the website also contains the basic information like the file name of the Excel attachment.

<img width="421" height="462" alt="image" src="https://github.com/user-attachments/assets/88b8e8c7-f0b6-4784-821e-cadbd6afba96" />

##### Q3. Investigate the Excel attachment. What is the SHA256 hash value?

Once the link is clicked, another window will pop up containing the different Hashes of the Excel File.

<img width="1274" height="823" alt="image" src="https://github.com/user-attachments/assets/43c15bf9-9ac9-468e-bec1-396260e0b60d" />

##### Q4. Check out the ANYRUN text report. What IP address is associated with the malicious domain biz9holdings.com?
To generate the text report, I clicked on the **Results** button, then navigate to the text report that will open another window.

<img width="1270" height="944" alt="image" src="https://github.com/user-attachments/assets/8b37a32c-370f-4b0b-81ae-3afc50630bd9" />

From there you can search the domain, and immediately find the IP address that is associated with it.

<img width="1269" height="708" alt="image" src="https://github.com/user-attachments/assets/399fa256-f0db-42f1-9f25-e8ba3d4590b2" />


##### Q5. Which other domain is classified as malicious?

Other domain tagged as malicious is also shown in the HTTP request

<img width="1105" height="276" alt="image" src="https://github.com/user-attachments/assets/64eecf27-9d88-416f-acc3-7e88c6c0ca7c" />


##### Q6. What vulnerability does this malicious attachment attempt to exploit?

In the behavior activities, it shows that this excel attachment attempt to exploit CVE-2017-11882

<img width="1135" height="466" alt="image" src="https://github.com/user-attachments/assets/4d77b86e-8cd2-47c4-ae77-c119315237ec" />

### Final Thoughts/Learnings
- If I were familiar with ANYRUN, it would be easier for me to navigate. On the bright side, it was fun navigating and exploring the website, which makes me better understand the important functions in analyzing phishing emails.
- I actually like the interface of ANYRUN, although it was overwhelming with the details. Once you get used to it, it's kind of easy to analyze and navigate.
