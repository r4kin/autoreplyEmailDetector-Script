# autoEmailDetector

Introduction -------------
The Apex Class, "autoEmailDetector_SCRIPT.txt", is intended to use Salesforce Metadata todetect autoreply emails that could cause feed back loops in Report a Problem. Using a custom Metadata object, 
"Autoresponse_Blacklist_mdt", which is populated by records containing key words that indicate an autoreply email (ex. "On vacation"). Using Apex SOAP API, iterate through Metadata object and create
list of key words. Email cases are then iterated through, and checked to see if it contains any key words. If a key word is found in the comments of a case, an error message is outputted to the 
Salesforce case. 

Requirements--------------  
- Salesforce Sandbox
- Populated Autoresponse Blacklist Metadata Object

Steps---------------------
1) Create Apex Class "YRK_Autoemail_Detector", copying code from "autoEmailDetector_SCRIPT.txt" 
2) Create Metadata Object labeled "Autoresponse Email", with object name "Autoresponse_Blacklist"
3) Create one custom field labeled "Body Text", with object name "Body_text"
4) Click "Manage Autoresponse Emails" and create new records labeled key words that could indicate an autoreply. A following defalt list is provided: Auto response, Automated reply, Automated response, Autoreply, Autoresponse, Away from office, Do not reply, Out of office, Undeliverable, Vacation 
5) Call method "detectAutoresponse()" 
