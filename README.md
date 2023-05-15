Sample Jenkins Pipeline
=======================

This repo helps to install Jenkins and the very first simple build pipeline for CI/CD. Just follow these steps:

1. **Install Jenkins** v2.337 or newer.
   - For Linux snaps execute: `snap install --edge --classic jenkins`
   - Otherwise: download and install it from: https://jenkins.io/download
2. **Launch Jenkins**
   - Then browse with your Web browser to: http://YOURHOSTNAME:8080
3. **Unlock Jenkins** 
   - Execute `sudo cat /DISPLAYED/PATH/TO/initialAdminPassword` to show the admin password
   - Enter the admin password to unlock Jenkins
4. Click on **'Select plugins to install'** and add these plugins:
   - 'Build Name and Description Setter'
   - then click **Install** and wait until installation has finished.
5. **Create the admin account** by entering name, password (twice), and full name.
6. **Enter your Jenkins URL**
7. Click **'Create element'**, then choose 'Pipeline'.
8. Click on 'Build now'
