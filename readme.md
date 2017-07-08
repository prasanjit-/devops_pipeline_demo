# # Jenkins Complete CI/CD Pipeline Demonstration # 


----------

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
