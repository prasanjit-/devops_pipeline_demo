# Demonstration for CI/CD deployment pipeline using Jenkins  
### | Subscribe & Learn DevOps for Free! [![BINPIPE](https://img.shields.io/badge/YouTube-red.svg)](https://www.youtube.com/channel/UCPTgt4Wo0MAnuzNEEZlk90A)
---

`Learning Resources for DevOps, SRE, Cloud & Engineering Management`

[![BINPIPE](https://img.shields.io/badge/BINPIPE-YouTube-red)](https://www.youtube.com/channel/UCPTgt4Wo0MAnuzNEEZlk90A)
[![Learn DevOps!](https://img.shields.io/badge/BINPIPE-Learn--DevOps-orange)](https://github.com/BINPIPE/resources/blob/master/devops-lesson-plans.md)
[![BINPIPE](https://img.shields.io/badge/Live--Classroom-blue)](https://forms.gle/tDJxDyj2nJyfsgsk7)
---


**Deliverables**:
This demonstration will simulate a completely automated CI/CD deployment pipeline using Jenkins. It will essentially do the following steps (phases):
1. Pull the source code for a Java EE based Project from GIT. (SCM AUTOMATION)
 2. Compile (build) the code using Maven to generate the .war file (BUILD AUTOMATION)
 3. Run Test cases & ensure they pass. (TEST AUTOMATION)
 4. Copy the .war to a Docker build workspace (DEPLOYMENT AUTOMATION)
 5. Build a Docker image for Jboss server to run the war file. (DEPLOYMENT AUTOMATION)
 6. Deploy the Docker container on a target node. (DEPLOYMENT AUTOMATION)

**Prerequisites**:
This demonstration has the following prerequisites:
 1. Jenkins should be installed with git, maven and shell plugins.
 2. In Jenkins Server install using # yum -y install git maven docker before trying out this demo.
 3. Changes to be made for Jenkins to be able to run docker.
 
```
echo "jenkins ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers
echo 'Defaults:jenkins !requiretty' >> /etc/sudoers
setenforce 0 # Else disable SELINUX in /etc/sysconfig/selinux  and reboot
 ```
 **Execution**:
Add a Jenkins Build Job As per the below screenshot and build it:
 - Note: Add the build commands from the **jenkins_build_commands.md** file.

![Jenkins build job](https://github.com/prasanjit-/devops_pipeline_demo/blob/master/images/Jenkins01.png)
![Jenkins build job](https://github.com/prasanjit-/devops_pipeline_demo/blob/master/images/jenkins02.png)
![Jenkins build job](https://github.com/prasanjit-/devops_pipeline_demo/blob/master/images/jenkins03.png)
![Jenkins build job](https://github.com/prasanjit-/devops_pipeline_demo/blob/master/images/jenkins04.png)
![Jenkins build job](https://github.com/prasanjit-/devops_pipeline_demo/blob/master/images/jenkins05.png)
___


<pre>
<a href="https://www.binpipe.org">BINPIPE</a> aims to simplify learning for those who are looking to make a foothold in the industry. 
Write to me at <b>nixgurus@gmail.com</b> if you are looking for tailor-made training sessions. 
For self-study resources look around in this repository, <a href="https://www.binpipe.org/">the Binpipe Blog</a> and <a href="https://www.youtube.com/channel/UCPTgt4Wo0MAnuzNEEZlk90A">Youtube Channel</a>.
</pre>

___
:ledger: Maintainer: **[Prasanjit Singh](https://www.linkedin.com/in/prasanjit-singh)** | **www.binpipe.org**
___

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

