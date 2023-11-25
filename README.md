How to install Jenkins and a Pipeline
=====================================

This repo contains step-by-step instructions to install [Jenkins](https://jenkins.io) and your first sample [Pipeline](https://www.jenkins.io/doc/book/pipeline/) for continuous integration and deployment (CI/CD).

1. **Install the Jenkins server**   
   - For Snaps execute: `sudo snap install --edge --classic jenkins`
   - For Docker execute: `docker run -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts-jdk11`
   - Otherwise download and install it from: https://jenkins.io/download

   NOTE: Pipeline support has been introduced in Jenkins version 2.337 or newer.

3. **Browse to your new Jenkins server**
   - Launch your Web browser and enter the URL: **http://HOSTNAME:8080**

   NOTE: Replace HOSTNAME by the computer name where Jenkins has been installed.

5. **Unlock Jenkins** 
   - Execute `sudo cat /DISPLAYED/PATH/TO/initialAdminPassword` to display the initial password saved by Jenkins.
   - Enter the initial password to unlock Jenkins.

6. **Install necessary Plugins**
   - Click on **'Select plugins to install'**
   - Add these plugins: **'Build Name and Description Setter'**
   - Click **Install** and wait until the installation has finished.
  
   NOTE: In case you miss something just visit: https://plugins.jenkins.io/ to discover more than 1800 plugins to extend your Jenkins installation. Sometimes a Jenkins restart is necessary after installing or refreshing plugins.

7. **Create the Administrator Account**
   - Enter the username, password (twice), and the full name.
   - Afterward, enter your Jenkins URL and log in.
     
8. **Create a Pipeline**
   - Click on **+ Create element** (left side).
   - Enter a job name (e.g. "sample-pipeline") and select **Pipeline**, then press the OK button.
   - The job configuration is displayed now - scroll down and select the **Pipeline script**.
   - As script enter the content of the **Jenkinsfile** (attached to this repository).
   - Click the **Save** button.
     
9. **Start a Pipeline Job**
   - Click on **Dashboard** (left side).
   - In your job list press the green **Play** button (right side).

📧 Feedback
------------
Send your email feedback to: markus.fleschutz [at] gmail.com

🤝 License & Copyright
-----------------------
This open source project is licensed under the CC0 license. All trademarks are the property of their respective owners.
