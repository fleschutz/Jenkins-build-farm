Sample Pipeline 'Hello World' for Jenkins
=========================================

This repo contains step-by-step instructions to install [Jenkins](https://jenkins.io) and the very first sample [Pipeline](https://www.jenkins.io/doc/book/pipeline/) for continuous integration and deployment (CI/CD).

1. **Install the Jenkins server**   
   - For Snaps execute: `sudo snap install --edge --classic jenkins`
   - For Docker execute: `docker run -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts-jdk11`
   - Otherwise download and install it from: https://jenkins.io/download

   NOTE: Pipeline support has been introduced in Jenkins version 2.337 or newer.

3. **Browse to your Jenkins server**
   - Launch your Web browser and enter the URL: http://HOSTNAME:8080  (replace HOSTNAME by the computer name where Jenkins has been installed)

4. **Unlock Jenkins** 
   - Execute `sudo cat /DISPLAYED/PATH/TO/initialAdminPassword` to display the initial password.
   - Enter the initial password to unlock Jenkins.

5. **Install necessary Plugins**
   - Click on **'Select plugins to install'** and add these plugins:
   - 'Build Name and Description Setter'
   - then click **Install** and wait until installation has finished.

6. **Create the admin account**
   - Enter the username, password (twice), and the full name.

7. **Enter your Jenkins URL**
8. Click **'Create element'**, then choose 'Pipeline'.
9. Click on 'Build now'

📧 Feedback
------------
Send your email feedback to: markus.fleschutz [at] gmail.com

🤝 License & Copyright
-----------------------
This open source project is licensed under the CC0 license. All trademarks are the property of their respective owners.
