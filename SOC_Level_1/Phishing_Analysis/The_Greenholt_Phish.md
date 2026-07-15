# Room Overview

a. Room Name: The Greenholt Phish

b. Difficulty: Easy

c. Tools Covered: Phishing Analysis, SPF, DMARC, VirusTotal, Message Source

### Objectives
- Analyze the provided email to identify and extract key artifacts
- Investigate the message source to determine its origin and authenticity
- Use analysis tools to assess the potential maliciousness of the email

### Thoughts/Completion Process

#### A Message That Doesn't Add Up

##### Q1. What is the Transfer Reference Number listed in the email's Subject line?
Upon loading challenge.eml, the reference number can be seen in the email subject line.

<img width="847" height="827" alt="image" src="https://github.com/user-attachments/assets/14baa278-5ed1-4925-8f3b-6f99c8dba63b" />

##### Q2. What is the display name of the sender?
Display name can also be seen in the top left corner of the email.

<img width="851" height="142" alt="image" src="https://github.com/user-attachments/assets/eb8cb787-ee09-4a97-9cca-255b9c93901d" />

##### Q3. Continue investigating the email headers. What is the sender's email address?

Email address can also be seen under the email sender's name.

<img width="844" height="141" alt="image" src="https://github.com/user-attachments/assets/706c9809-5a53-4ab2-8c99-7ff6f338ef33" />

##### Q4. What email address will receive a reply to this email?

The reply to part of the email contains the email address that will receive a reply to the email.

<img width="848" height="144" alt="image" src="https://github.com/user-attachments/assets/a7e0c9ac-48d5-4bbd-b0fc-4430959b7c8b" />

##### Q5. Begin analyzing the message source. What is the originating IP address of this email?

I began analyzing the message source using the shortcut CTRL+U.

Under the details in the X-Originating IP, you can see the originating IP of this email.

<img width="673" height="121" alt="image" src="https://github.com/user-attachments/assets/3af91665-f93f-4910-85f2-9bbc5139ae7c" />

##### Q6. Investigate the IP address from the previous question. Who is the owner of the originating IP?

I kind of struggled in this part that I forgot what website should I use to find the IP owner.

I used WHOIS and searched up the IP address:

<img width="517" height="287" alt="image" src="https://github.com/user-attachments/assets/a2ffe008-ef89-4c88-88f6-a1abfece0476" />

##### Q7. Run an SPF record check on the Return-Path domain identified in the email headers. What is the full SPF record for this domain?

Using the SPF website https://dmarcian.com/spf-survey/, I ran through the domain "https://dmarcian.com/spf-survey/" and got this as a result:

<img width="532" height="159" alt="image" src="https://github.com/user-attachments/assets/4b7a4a0a-8cc4-4184-b7f6-2ddf8a977c25" />

##### Q8.Perform a DMARC lookup for the Return-Path domain found in the email headers. What is the complete DMARC record for this domain?

Since the provided website of TryHackMe has a 30 days trial, I used an alternative website that provided the DMARC record for mutawamarine.com

<img width="752" height="360" alt="image" src="https://github.com/user-attachments/assets/cfc5c008-c8c8-45e7-813e-d82ef07d409f" />

##### Q9. What is the file name of the attachment found in the email?

To make it easier to find the file, I used the search function and type in "attachment"

<img width="626" height="299" alt="image" src="https://github.com/user-attachments/assets/d6ef5883-d017-4c93-86fe-b854424cf1ae" />

##### Q10.Download the attachment to your virtual environment. Using the sha256sum command, what is the SHA256 hash of the file?

Once the file is downloaded, I ran through it in the terminal:

<img width="800" height="62" alt="image" src="https://github.com/user-attachments/assets/559e7c46-7d3d-450b-82a4-df3d01bf6e40" />

##### Q11.Investigate the file hash from the previous question using VirusTotal. What is the attachment's file size in KB (e.g., 122.31 KB)?

I went to the VirusTotal website and pasted the file hash:

<img width="1646" height="289" alt="image" src="https://github.com/user-attachments/assets/164304b1-1b8e-4df5-95d7-3f6c48e7c6f9" />

##### Q12. Continue your research on the file. What is the actual file type of the attachment?

It can also be seen in the VirusTotal website that it is a rar attachment 

<img width="1577" height="200" alt="image" src="https://github.com/user-attachments/assets/99af5b75-825c-4f6e-b7c4-1d01e7baeb88" />

### Final Thoughts/Learnings
- I actually think that this room teaches more about being keen in the details of what is being analyzed.
- Also being familiar with the tools that you will use in analyzing emails like DMARC, VirusTotal, SPF, and Message Source.
