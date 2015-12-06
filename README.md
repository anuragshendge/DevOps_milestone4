# CSC 591/791 Milestone 4 - Special Miletstone
## Team members
1. Anurag Shendge (ashendg)  
2. Aneesh Kher (aakher)
3. Krishna Teja Dinavahi (kdinava) 

- - - 
 
## Overview
In the fourth and final special milestone, we demonstrate the entire end to end pipeline of the application and then demo the special component in the pipeline. We have used a simple node application for the purpose of this pipeline. All it does is serve simple HTML webpages on GET request(s). 
The screencast for the milestone is linked at the [end of this page](https://github.com/anuragshendge/DevOps_milestone4#screencast). In the screencast, we present [**Build**](https://github.com/aneeshkher/DevOpsMilestone1), [**Test and analysis**](https://github.com/anuragshendge/milestone2) and [**Deployment**](https://github.com/anuragshendge/DevOpsMilestone3) steps in the milestone. At last we demo the special component(s) namely a **_Doctor Monkey_** and **_Maintenance Monkey_**. 

## Milestone break up

1.	**Build**: In the build phase, we used  a script to automatically provision the AWS intances. Ansible playbook was used to configure these AWS instances which would be used as  prodcution server and a canary server. We use _Jenkins-CI_ as the build tool for the pipeline. A build is triggered as soon as the code is commited via a post commit hook.

2.	**Test and Analysis**: Test and Analysis phase will check that if the application passes the unit tests. We have used _Mocha JS_ and _Chai_JS_ testing frameworks for checking if the unit tests pass. In addition to that, we have also included an analysis component which check for the code coverage using _Istanbul_ and any coding style errors and deviation from best coding practices using _JS Hint_. We make sure that no build is passed succesully unless it meets the analysis critea (which is custom set and can be changed as per the project requirement).
3. **Deployment**: In the deplyment phase, we have used a _Canary_ approach where in 66% of the incoming requests are routed to the prodcution server and rest of the 33% are routed to Canary. We also integrated _feature flags_ which basically can turn on or turn off a feature in the application. This way we have a manual override over a feature without taking down the running server. We user _redis server_ as out global key-value store. We also sent custom alerts in the form of SMS messages whenever a spike in CPU usage was detected in the CPU or excessive memory usage occured. We used Twilio service to send and receive SMS alerts.

4. **Special Milestone**: In the special milestone we have implemented two kinds of Monkeys.
	- **Doctor Monkey** : The doctor monkey will act as a security guard for the production server. Basically, it acts as a safegaurad against any processes hogging unreasonable large amount of CPU. As an extension to milestone 3 functionality to send alerts, the doctor monkey also tries to take care of the problem then and there itself. It does so by terminating the process which is causing the high CPU usage. The monkey ensures that the process which is being terminated is not a **_root_**	or **_admin_user_** process. An alert in the form of an email message is sent to the stakeholders.
	- **Maintenance Monkey** : On the other hand, manintenance monkey keeps a check in the system resources. As a proof of concept, we have demonstrated _disk space usage_ as a system resource which is continously monitored. As the threshold for the maximum allowed file size reaches, the monkey comes into action and **backs up** the log file onto a **secondary storage server**. After that it deletes the log file from the production server. The maintenance monkey hence ensures that the main production server never runs out of space. The files which are chosen to be deleted are strcitly secondary files such as logs and system dumps and the application, database files are left untouched by the monkey as they could be critical for the application functionality.

- - -
#Screencast   
###(Click the image below  and you will be redirected to YouTube)
[![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/GtowTXDaQf0/0.jpg)](https://youtu.be/GtowTXDaQf0)



 
