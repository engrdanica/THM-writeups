### Room Overview
<img width="997" height="810" alt="image" src="https://github.com/user-attachments/assets/cf5ecb2e-d450-4f60-acce-9e2939c73cbe" /><img width="997" height="810" alt="image" src="https://github.com/user-attachments/assets/360b14e8-8b8d-48c1-a076-0c1479873de2" /><img width="997" height="810" alt="image" src="https://github.com/user-attachments/assets/ee979e04-d1ca-4d23-8fa3-fd0c51f01865" /><img width="997" height="810" alt="image" src="https://github.com/user-attachments/assets/d9a07a0c-db52-4f9b-8a7d-b9943d2c0272" />### Room Overview

a. Room Name: Splunk: The Basics

b. Difficulty: Easy

c. Tools Covered: Splunk

### Objectives
- Understanding the components of Splunk
- Exploring some available options in Splunk
- Understanding log ingestion in Splunk
- Practically ingesting some Logs in Splunk and analyzing them

### Thoughts/Completion Process

#### Machine Overview
I will soon configure the machine on my local computer, but for now I will use the TryHackMe Attackbox
Splunk can be accessed at <Machine IP> 

<img width="1092" height="907" alt="image" src="https://github.com/user-attachments/assets/bc655ac5-cc97-4fc5-8930-4bed4cd39d6e" />

There are also instructions provided by TryHackMe on how to upload data successfully, which are:

**To upload the data successfully, you must follow five steps, which are explained below:**
1. Select Source: Choose the Log file and the data source.
2. Select Source Type: Select what type of logs are being ingested, e.g, JSON, syslog.
3. Input Settings: Select the index where these logs will be dumped and the HOSTNAME to be associated with the logs.
4. Review: Review all the configurations.
5. Done: Complete the upload. Your data will be uploaded successfully and ready to be analyzed.

##### Q1. Upload the data attached to this task and create an index "VPN_Logs". How many events are present in the log file?
So it basically said that the log file is available in the **/root/Rooms/SplunkBasic/** directory

<img width="1089" height="874" alt="image" src="https://github.com/user-attachments/assets/d9257cfc-747f-4ac3-90df-b544ae669972" />

After adding the data, I leave the source type as is since it's already in JSON format

<img width="1050" height="808" alt="image" src="https://github.com/user-attachments/assets/884f3f03-d177-40d7-b416-89673d536389" />

Following the instructions, I have created an index "VPN Logs".
<img width="1089" height="909" alt="image" src="https://github.com/user-attachments/assets/dda3abad-d18f-4d03-86e2-181eecd94d7a" />

Then I submitted and started searching. As always, you navigate and be keen on the details presented in the dashboard; I immediately saw the number of events: 2,862 events.

<img width="1399" height="907" alt="image" src="https://github.com/user-attachments/assets/5c2a1bfe-75a7-4fc6-87d8-414002bd955b" />

##### Q2. How many log events are captured by the user Maleena?

I looked at the events and the Field IDs, then saw that I can query the user "Maleena", but looking at the left side pane, you can see all the fields.
- I clicked on the UserName field and saw the values; 10 log events are captured by user Maleena.

<img width="997" height="810" alt="image" src="https://github.com/user-attachments/assets/0a1e2a75-ed8c-41e2-bfa1-e0d6c8541622" />


##### Q3. What is the username associated with IP 107.14.182.38?

I checked the left side pane for the source IP, but this time I just queried it from the search bar and found the user "Smith"

<img width="1032" height="871" alt="image" src="https://github.com/user-attachments/assets/3af2f0a5-d9fd-4494-b9a3-eea858592e2a" />

##### Q4. What is the number of events that originated from all countries except France?
So I noticed that it was quite like SQL, so I tried **" Source_Country != "France" "**

<img width="1031" height="866" alt="image" src="https://github.com/user-attachments/assets/c1d2f344-1dab-428a-b269-9dcb1dcbded5" />


##### Q5. How many VPN events were associated with the IP 107.3.206.58?
Same as Q3, I searched for the source IP "107.3.206.58" and located the number of events.

<img width="1034" height="875" alt="image" src="https://github.com/user-attachments/assets/e8c80c28-c54c-4a79-af02-a5e10039e9ac" />

### Takeaways
| Terms/Command | Description |
|----|----|
| Splunk Forwarder | lightweight agent installed on the endpoint intended to be monitored, and its main task is to collect the data and send it to the Splunk instance |
| Splunk Indexer | parses and normalizes the data into field-value pairs, categorizes it, and stores the results as events |
| Splunk Search Head | where users can search the indexed logs |
| Splunk Index | repository that stores your organization's machine data |

### Final Thoughts/Learnings
I actually think that the Splunk dashboard looks like Google Cloud and MS Power BI combined, so it was more on familiarity and exploration at this point. Everything feels like you have to navigate, take notes on what the tabs are for, and investigate and understand what is going on. Also, this can help me work out my SQL skills in the long run. I thought Splunk was heavy on numbers, but it actually looks friendly for beginners like me in Splunk. 
