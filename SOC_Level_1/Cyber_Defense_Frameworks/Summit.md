### Room Overview

a. Room Name: Summit

b. Difficulty: Easy

c. Tools Covered: Pyramid of Pain, Mitre

### Objectives
- Following the Pyramid of Pain's ascending priority of indicators, your objective is to increase the simulated adversaries' cost of operations and chase them away for good. Each level of the pyramid allows you to detect and prevent various indicators of attack.

### Thoughts/Completion Process

#### Given Dashboard

Navigate to the given link: [https://LAB_WEB_URL.p.thmlabs.com](https://10-49-140-77.reverse-proxy.cell-prod-ap-south-1b.vm.tryhackme.com)

##### Q1. What is the first flag you receive after successfully detecting sample1.exe?

After you navigate to the website provided, you'll see the dashboard

<img width="1120" height="791" alt="image" src="https://github.com/user-attachments/assets/b12cc192-92be-4990-af2b-28a30c8046e8" />

I then went to the Malware Sandbox to analyze sample1.exe

<img width="1123" height="789" alt="image" src="https://github.com/user-attachments/assets/7490482e-a13a-4f4e-a354-d6478c3518ad" />

So the email says that we should be able to add a detection rule to block it out. As you can see, it has hashes that we could block in the Manage Hashes Tab.

<img width="1119" height="735" alt="image" src="https://github.com/user-attachments/assets/c039d380-fd65-42f7-9d4c-6ea6d545c1c4" />

I put SHA256 and immediately received the second email.

<img width="1107" height="540" alt="image" src="https://github.com/user-attachments/assets/7664227e-9556-45b2-b41d-b82b8731a8ed" />

Then, after submitting the hash in the Manage Hashes tab, I received another email containing the second instruction as well as the answer for number 1.

<img width="1122" height="745" alt="image" src="https://github.com/user-attachments/assets/72bddf40-8ab4-4703-b1f9-c8511f232bb4" />

##### Q2. What is the second flag you receive after successfully detecting sample2.exe?

In the second one, since we managed to use the Manage hashes tab, I figured I could use the Firewall Rule Manager by using the data analyzed in sample2.exe

<img width="1122" height="743" alt="image" src="https://github.com/user-attachments/assets/1272d2cc-9dbe-49a8-a820-0979eabcd6c3" />

So, according to the earlier data, the destination IP points to a mysterious URL.  So we won't allow any Source IP to connect from our Desination IP

<img width="1120" height="791" alt="image" src="https://github.com/user-attachments/assets/661c1ade-b87f-4a9b-8911-6dffffc0091f" />

Then after that we'll receive our second flag

<img width="713" height="523" alt="image" src="https://github.com/user-attachments/assets/5baeb1a3-0fa9-4137-87cb-efe6e6e2da12" />

##### Q3. What is the third flag you receive after successfully detecting sample3.exe?

We now analyze the sample3.exe from the Malware Sandbox

<img width="1122" height="792" alt="image" src="https://github.com/user-attachments/assets/f6ae15a8-48a0-4a13-9364-42b75cb98b93" />

I headed to the DNS filter since we found a mysterious domain from our analysis

<img width="1121" height="791" alt="image" src="https://github.com/user-attachments/assets/2933a8c3-0e95-41b6-b1a7-8609f0f1f4a6" />

I entered the domain and named it "Malware Download" since, in the behavior analysis, it downloads executable files from the internet

<img width="1118" height="658" alt="image" src="https://github.com/user-attachments/assets/c03aabcd-7961-4c0c-b51c-65e77a338414" />

Then we'll receive another email that contains the 3rd answer
<img width="1099" height="647" alt="image" src="https://github.com/user-attachments/assets/a3054682-c27d-4681-aba5-c125c7e6f99b" />

##### Q4. What is the fourth flag you receive after successfully detecting sample4.exe?

Upon checking its behavior, it disables Windows Defender real-time monitoring and also makes changes to the registry.

<img width="1121" height="741" alt="image" src="https://github.com/user-attachments/assets/fccd35c2-8198-4b82-b239-9738a754bdad" />

I am also new to Sigma Rule Builder, so I will try to explore it more. There are 4 types of rules here, but I do think that registry logs don't apply to Web Server Logs, Application Logs, and VPN Logs.

That makes me choose the Sysmon Event logs. 

<img width="436" height="621" alt="image" src="https://github.com/user-attachments/assets/f67388b3-0cb9-4253-8c9d-d38992dfbc8d" />

The next step is choosing an event; since we're talking about registry logs, I went to choose Registry modifications.

<img width="456" height="755" alt="image" src="https://github.com/user-attachments/assets/6d943fdd-8557-4d73-a457-a97ae39d5b45" />


Going back to Malware Sandbox, we can see in the registry activity the event where it modified the registry to disable Windows Defender.

<img width="708" height="457" alt="image" src="https://github.com/user-attachments/assets/006f3009-5958-4257-b348-a447b464acd1" />

On to the next step, we have to enter the details. If I didn't read about Defense Evasion, I would've chosen Persistence since it's also about registry change, but then again the topic is about Disabling Windows Defender, which is evading the PC's defenses.

<img width="453" height="441" alt="image" src="https://github.com/user-attachments/assets/c3c4a2b8-bd40-4ce4-ae16-e6678342b76f" />

After submitting the rule, it would look like this:

<img width="1121" height="660" alt="image" src="https://github.com/user-attachments/assets/730c70c3-05ad-4a17-986b-05c8f5584a08" />

Then I received another email from Sphinx

<img width="1121" height="741" alt="image" src="https://github.com/user-attachments/assets/8fc2dd36-f7eb-4204-bccc-6239a562a45c" />

##### Q5. What is the fifth flag you receive after successfully detecting sample5.exe?

The message has confirmed that we have to be keen about the details and their activity. So I double-clicked the logs:

<img width="1122" height="794" alt="image" src="https://github.com/user-attachments/assets/4f32ae44-4400-4e6c-8f71-2b449328f44b" />

I have observed that it has been recurring every 30 minutes with the same Port 443, Destination IP of 51.102.10.19, and byte size of 97.

While exploring Sigma Rule Builder, under Sysmon Event logs, you'll see the Network Connections

<img width="464" height="756" alt="image" src="https://github.com/user-attachments/assets/40b770e7-01b2-4e76-a74d-e270897dea00" />

Then I filled in the details. By the way, I also tried using Port 443, but I was incorrect, so I tried using any port just to make sure, and that was right.

<img width="434" height="457" alt="image" src="https://github.com/user-attachments/assets/2d460c53-0bcd-4317-931f-b072135f0b96" />

After that, I received an annoyed Sphinx email
<img width="715" height="584" alt="image" src="https://github.com/user-attachments/assets/afa297cf-1ada-41a3-8d89-8af6496e857b" />

##### Q6. What is the final flag you receive from Sphinx?

I viewed the commands.log from Sphinx and saw that it is sending data to %temp%\exfiltr8.log file.
<img width="1124" height="794" alt="image" src="https://github.com/user-attachments/assets/1e2432db-98c3-4065-bfbc-2aeb810b30b3" />

As we can see here, it has created a file in the temp directory
<img width="1124" height="796" alt="image" src="https://github.com/user-attachments/assets/5cd5768e-6f2b-4be2-8691-af25f126353b" />

Again, I used the Sigma Rule Builder and chose File Creation and Modification

<img width="494" height="792" alt="image" src="https://github.com/user-attachments/assets/aa091673-495e-47d9-9c56-e2b33f9591bc" />

<img width="436" height="312" alt="image" src="https://github.com/user-attachments/assets/16316a9d-5570-4974-8dc2-163e33f6ab74" />

Which was correct and got the last answer.

### Final Thoughts/Learnings
Actually, I kind of struggled at the end part where you have to use the Sigma Rule Builder and analyze what the details really are that you have to focus on. In the end, it shows where I should study more. 
