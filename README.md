# CSC 591/791 Milestone 4 - Special Miletstone
## Team members
1. Anurag Shendge (ashendg)  
2. Aneesh Kher (aakher)
3. Krishna Teja Dinavahi (kdinava) 

- - - 
 
## Overview
In the fourth and final special milestone, we demonstrate the entire end to end pipeline of the application and then demo the special component in the pipeline. We have used a simple node application for the purpose of this pipeline. All it does is serve simple HTML webpages on GET request(s). 
The screencast for the milestone is linked at the end of this page. In the screencast, we present **_Build_**, **_Test and analysis_** and **_Deployment_** steps in the milestone. At last we demo the special component(s) namely a **_Doctor Monkey_** and **_Maintenance Monkey_**. 

## Milestone break up

1.	**Build**: In the build phase, we used  a script to automatically provision the AWS intances. Ansible playbook was used to configure these AWS instances which would be used as  prodcution server and a canary server. We use _Jenkins-CI_ as the build tool for the pipeline. A build is triggered as soon as the code is commited via a post commit hook.

2.	**Test and Analysis**: Test and Analysis phase will check that if the application passes the unit tests. We have used _Mocha JS_ and _Chai_JS_ testing frameworks for checking if the unit tests pass. In addition to that, we have also included an analysis component which check for the code coverage using _Istanbul_ and any coding style errors and deviation from best coding practices using _JS Hint_. We make sure that no build is passed succesully unless it meets the analysis critea (which is custom set and can be changed as per the project requirement).
3.	** Deployment**: In deplyment phase, we have used a _Canary_ approach 






