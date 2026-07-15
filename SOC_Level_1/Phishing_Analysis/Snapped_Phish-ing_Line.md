# Room Overview
a. Room Name: Snapped Phish-ing Line

b. Difficulty: Easy

c. Tools Covered: CyberChef, Message Source, VirusTotal

### Objectives
- Analyze the provided email samples to identify key artifacts
- Investigate phishing URLs to understand redirection
- Retrieve and examine the phishing kit used in the attack
- Use CTI tools to gather intelligence on the adversary
- Analyze the phishing kit to uncover additional indicators

### Thoughts/Completion Process

#### A Series of Suspicious Emails

##### Q1. Begin reviewing the emails in the phish-emails folder on your desktop. Which individual received the email regarding a Quote for Services Rendered?

There's 5 emails in the folder, but I reviewed first the filename of each email.

One email contains "Quote for Services Rendered..."

<img width="790" height="885" alt="image" src="https://github.com/user-attachments/assets/eff92f62-4ef1-4a12-8fd8-1ec04580448d" />

##### Q2. What email address was used by the adversary to send the phishing emails?

The email address used can be seen at the top from the header of the email.

<img width="792" height="721" alt="image" src="https://github.com/user-attachments/assets/9e44cba1-b704-4cc0-9ac4-f360a472278b" />

##### Q3. Investigate the attachment in the email addressed to Zoe Duncan. What is the root domain of the redirection URL found within the file?

In the folder, I find the email addressed to Zoe Duncan

<img width="856" height="598" alt="image" src="https://github.com/user-attachments/assets/279a3774-2196-4566-af76-f7b7b096493d" />

Then I tried finding the redirection URL in the message source but I couldn't find one. Then I downloaded the file and opened it in text editor

<img width="789" height="347" alt="image" src="https://github.com/user-attachments/assets/07561151-bf42-4e93-81b0-51217816eb0b" />


##### Q4. Open the attachment in your VM web browser. Which company is the login page impersonating?

I double clicked the downloaded attachment, and saw that it was impersonating Microsoft

<img width="800" height="545" alt="image" src="https://github.com/user-attachments/assets/bb34a27b-1724-48f2-880d-807af0a2b741" />

##### Q5. Let’s check if the attacker left any files exposed on the same website. Navigate to the /data directory. What is the name of the archive file?

I changed the directory to /data, then saw that there is an archive file named Update365.zip

<img width="795" height="371" alt="image" src="https://github.com/user-attachments/assets/4647f9bf-b9c1-485e-9bc6-ef2e99b81f8e" />

##### Q6. Download the phishing kit archive to your virtual environment. Using the sha256sum command, what is the SHA256 hash of the file?

I downloaded the archive file and use the terminal to generate the SHA256 of the file.

<img width="713" height="34" alt="image" src="https://github.com/user-attachments/assets/ef3f88b8-6a2d-49f0-b4da-9cd9b244ebf6" />

##### Q7. Investigate the file hash from the previous question using VirusTotal. Aside from phishing, what other threat category is assigned to the ZIP archive?

I went to VirusTotal and paste the SHA256 of the file. 

<img width="1661" height="946" alt="image" src="https://github.com/user-attachments/assets/fa2ff511-f20e-4d57-822e-888b240bbb68" />


##### Q8.Review the VirusTotal Details page for the phishing kit. How many files are contained within the archive?

In VirusTotal>Details>Bundle Info>Contents Metadata, you can easily see the contained files

<img width="769" height="619" alt="image" src="https://github.com/user-attachments/assets/90639e6d-d957-47c5-a0c3-4a8751168877" />

##### Q9. Let’s see if the attacker has exposed any captured credentials. Navigate to the /data/Update365/ directory and investigate the log file. What is the email address of the user who submitted their credentials more than once

I went back to the website and navigated to the said directory and clicked the log file. Upon investigation, I found the user that has logged in more than once.

<img width="800" height="881" alt="image" src="https://github.com/user-attachments/assets/2044a631-391f-4389-867d-65792bd3747a" />

##### Q10. Extract the phishing kit archive and locate the submit.php file. What email address is used by the adversary to collect compromised credentials?

I extracted the phishing kit archive and explore until I found the submit.php file. Upon opening the file, I went digging up for the email that is used

<img width="795" height="852" alt="image" src="https://github.com/user-attachments/assets/7c8d25ee-c22c-4a73-9a03-869b8821fa90" />

##### Q11. Return to the phishing URL and locate the flag.txt file. Using CyberChef to decode the flag, what is the secret value?

This is quite tricky, when I tried going further in kennaroads[.]buzz/data/Update365/office365, there was a 404 error.

So first I tried kennaroads[.]buzz/data/Update365/flag.txt, but it didn't work.

Then I tried kennaroads[.]buzz/data/Update365/office365/flag.txt and it worked!

<img width="794" height="351" alt="image" src="https://github.com/user-attachments/assets/775f940c-f6ff-43ce-b675-293278012cb4" />

I copied the text and pasted in CyberChef to decipher:

<img width="903" height="585" alt="image" src="https://github.com/user-attachments/assets/745cd169-e0db-469c-8e11-9ba94a87d771" />

### Final Thoughts/Learnings
- This room was fun to do, since you get to explore and just try to get the information that you need.
- It's actually tricky on some parts especially on navigating the website and finding the flag and just like other rooms, you just need to explore and remember the tools that we have learned in the beginner courses.
