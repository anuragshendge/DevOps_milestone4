# CSC 591/791 Milestone 4 - Special Miletstone
## Team members
1. Anurag Shendge (ashendg)  
2. Aneesh Kher (aakher)
3. Krishna Teja Dinavahi (kdinava) 

- - - 
 
## Overview
In the fourth and final special milestone, we demonstrate the entire end to end pipeline of the application and then demo the special component in the pipeline. We have used a simple node application for the purpose of this pipeline. All it does is serve simple HTML webpages on GET request(s). 
The screencast for the milestone is linked at the end of this page. In the screencast, we present **_Build_**, **_Test and analysis_** and **_Deployment_** steps in the milestone. At last we demo the special component(s) namely a **_Doctor Monkey_** and **_Maintenance Monkey_**. 

- **Doctor Monkey** : The doctor monkey will act as a security guard for the production server. Basically, it acts as a safegaurad against any processes hogging unreasonable large amount of CPU. As an extension to milestone 3 functionality to send alerts, the doctor monkey also tries to take care of the problem then and there itself. It does so by terminating the process which is causing the high CPU usage. The monkey ensures that the process which is being terminated is not a **_root_**	or **_admin_user_** process. An alert in the form of an email message is sent to the stakeholders.


- **Maintenance Monkey** : On the other hand, manintenance monkey keeps a check in the system resources. As a proof of concept, we have demonstrated _disk space usage_ as a system resource which is continously monitored. As the threshold for the maximum allowed file size reaches,the monkey comes into action and backs up the log file onto a secondary storage server. After that it deletes the log file  from the production server. The maintenance monkey hence ensures that the main production server never runs out of space. The files which  are chosen to be deleted are strcitly secondary files such as logs and system dumps and the application, database files are left untouched by the monkey as they could be critical for the application functionality.
