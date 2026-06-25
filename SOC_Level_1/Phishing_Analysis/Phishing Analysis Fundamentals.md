### Room Overview

a. Room Name: Phishing Analysis Fundamentals

b. Difficulty: Easy

c. Tools Covered: Email, Cyberchef

### Objectives
- Learn the basics of email delivery
- Explore email header analysis
- Investigate and analyze email bodies
- Learn about the different types of phishing
- Analyze emails to identify potential security threats
  
### Thoughts/Completion Process

#### Email headers

##### Q1. What is the full subject line of email1.eml?

So I opened the email samples and email1.eml to start seeing the full subject line

<img width="713" height="854" alt="image" src="https://github.com/user-attachments/assets/538d0371-1c6f-484a-bfab-00254a82c0a3" />

You can easily see the subject once you've opened the email.

<img width="715" height="715" alt="image" src="https://github.com/user-attachments/assets/92802b18-0142-4f49-a284-a303c053e2dc" />

##### Q2. View the message source of email1.eml using Thunderbird in your VM. What the IP address listed as the X-Originating-Ip?

I used the shortcut Ctrl+U to see the message source.

<img width="713" height="857" alt="image" src="https://github.com/user-attachments/assets/babece9b-9c27-4ae4-836e-ff6f28a14bfe" />

#### Email body

##### Q1. Open up the email2.txt file to view the source of an attachment. What is the Content-Type of the attachment?
Once you've opened email 2.txt file, this will appear:

<img width="712" height="857" alt="image" src="https://github.com/user-attachments/assets/ec48787e-c536-4247-b05a-3eca26d01c07" />

You will easily see the content type at the top left corner of the txt file

<img width="714" height="854" alt="image" src="https://github.com/user-attachments/assets/e78846d4-07c3-4618-a0b8-6245f2b3d4b5" />

##### Q2. What is the name of the attachment from the previous question?

Together with the content type, you will see the filename too.

<img width="710" height="855" alt="image" src="https://github.com/user-attachments/assets/6368d27b-540e-46d7-a30b-fff9cbf2f56f" />

##### Q3. Decode the base64 string using either a PDF converter or CyberChef. What is the hidden flag value?

I used apivoid to decode the base64. I copied all the text from the top to the bottom

<img width="712" height="857" alt="image" src="https://github.com/user-attachments/assets/543fb409-c194-4967-8e53-de68ffa0ffe0" />

And this was the result:

<img width="1272" height="911" alt="image" src="https://github.com/user-attachments/assets/53683970-539f-4d1e-b133-58a9b5905204" />

#### Types of Phishing

##### Q1. Which reputable organization is being spoofed in this phishing attempt?

You'll end up on this page once you've opened the email3.eml

<img width="713" height="713" alt="image" src="https://github.com/user-attachments/assets/30cbacef-03c8-4be9-b60b-24c6c53700e2" />

In this email, they are trying to impersonate Home Depot.

<img width="715" height="713" alt="image" src="https://github.com/user-attachments/assets/8adc1cb1-ca27-483d-b11d-8959fc112565" />

##### Q2. What is the sender's email address?

They are using the email support@teckbe.com

<img width="715" height="713" alt="image" src="https://github.com/user-attachments/assets/1591e94d-1262-4f6d-91df-2c50b73feb6a" />

##### Q3. Inspect the email message source. What is the defanged X-Originating-IP?

Again, use the shortcut Ctrl+u, and find the X-originating IP

<img width="715" height="715" alt="image" src="https://github.com/user-attachments/assets/69fdd9f6-bddd-4aba-933b-52309c292697" />

After that, go to the Cyberchef website and paste the X-originating IP to get the defanged X-originating IP

<img width="1274" height="764" alt="image" src="https://github.com/user-attachments/assets/5b707357-856d-4775-ad6e-f8cef4db781b" />

##### Q4. Continue analyzing the email message source. Which mail server generated the Authentication-Results header?

Checked the message source for the authentication results and found out that atlas102.free.mail.gq1.yahoo.com is the mail server that generated the Authentication-Results.

<img width="513" height="408" alt="image" src="https://github.com/user-attachments/assets/f44c7466-354d-4d35-8536-8f0cee9f463e" />

### Takeaways
| Terms/Command | Description |
|----|----|
| Email header | Contains metadata about the message, such as the sender and the servers involved in delivery |
| Email body | Contains the actual message content, which may be plain text or HTML |
|Content-Type |indicates the file type application/pdf|
|Content-Disposition|specifies that the file is an attachment and includes its filename|
|Content-Transfer-Encoding |shows that the file is base64 encoded|

### Final Thoughts/Learnings
This chapter was the introduction, so it's expected that it was easy and more on navigation towards the email parts and using Cyberchef. A good part is that it's making you keen on the details and familiarize yourself with emails and using Cyberchef or other websites.
