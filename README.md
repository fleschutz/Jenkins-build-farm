Sample Jenkins Pipeline 'Hello World'
=====================================

This repo helps to install [Jenkins](https://jenkins.io) and the very first [Pipeline](https://www.jenkins.io/doc/book/pipeline/) for continuous integration (CI/CD). Just follow these steps:

1. **Install Jenkins**
   - Required is version 2.337 or newer
   - For Snaps execute: `sudo snap install --edge --classic jenkins`
   - For Docker execute: `docker run -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts-jdk11`
   - Otherwise download and install it from: https://jenkins.io/download

2. **Browse to Jenkins**
   - Launch your Web browser and enter: http://HOSTNAME:8080 (replace HOSTNAME by the computer name where Jenkins has been installed)

3. **Unlock Jenkins** 
   - Execute `sudo cat /DISPLAYED/PATH/TO/initialAdminPassword` to show the admin password
   - Enter the admin password to unlock Jenkins

4. **Install Plugins**
   - Click on **'Select plugins to install'** and add these plugins:
   - 'Build Name and Description Setter'
   - then click **Install** and wait until installation has finished.

5. **Create the admin account**
   - Enter the username, password (twice), and the full name.

6. **Enter your Jenkins URL**
7. Click **'Create element'**, then choose 'Pipeline'.
8. Click on 'Build now'
