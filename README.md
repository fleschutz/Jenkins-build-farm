Sample Pipeline
===============

This repo helps to install Jenkins and the very first simple Pipeline. Just follow these steps:

1. **Install Jenkins** v2.303.3 or newer.
   - For Linux snaps execute: `snap install --beta --classic jenkins`
   - Otherwise, download and install it from: https://jenkins.io/download
2. **Launch Jenkins** and browse to: http://YOURHOSTNAME:8080
3. **Unlock Jenkins** by entering the file content of the displayed file.
4. Click on **'Select plugins to install'** and add these plugins:
   - 'Build Name and Description Setter'
   - then click **Install** and wait until installation has finished.
5. **Create the admin account** by entering name, password (twice), and full name.
6. **Enter your Jenkins URL**
7. Click **'Create element'**, then choose 'Pipeline'.
8. Click on 'Build now'
