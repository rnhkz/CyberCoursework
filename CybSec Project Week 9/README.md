# Honeypot Assignment

**Time spent:** **5** hours spent in total

**Objective:** Create a honeynet using MHN-Admin. Present your findings as if you were requested to give a brief report of the current state of Internet security. Assume that your audience is a current employer who is questioning why the company should allocate anymore resources to the IT security team.

### MHN-Admin Deployment (Required)

**Summary:** MHN-Admin was deployed using AWS. A Ubuntu machine was created, then connected to through SSH. On MHN_Admin, python-magic gets installed, then MHN is installed after cloning the repository. Inbound rules are added for communication with the Honeypot.

<img src="mhn-admin.gif">

### Dionaea Honeypot Deployment (Required)

**Summary:** Dionaea is software which which is meant to trap malware being used against a network. A new instance was created within AWS, similarly to MHN-Admin. Afterwards, from the MHN website, a script is created from the "Deploy" section, which installs and sets up Dionaea. This script is ran from within the Dionaea instance.

<img src="dionaea-honeypot.gif">

### Database Backup (Required) 

**Summary:** MHN-Admin uses the database management system MongoDB. The exported JSON file records information about individual attacks, including timestamp, ip of attacker, source/destination port, and the honeypot attacked.

## Notes

Had an issue with mnenosyne not starting. After reading the error log, I discovered there was an error in the "hub.py" file preventing the service from running. I commented out code which verified greenlet version number, and spoofed a valid version instead. This fixed the issue.
