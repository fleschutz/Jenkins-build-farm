How to install Jenkins and a Pipeline
=====================================

This repo contains simple step-by-step instructions to install [Jenkins](https://jenkins.io) and a sample [Pipeline](https://www.jenkins.io/doc/book/pipeline/) for CI/CD (Continuous Integration and Continuous Delivery/Deployment).

🔧 Install the Jenkins server
------------------------------
* Execute for Docker: `docker run -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts-jdk11`
* Execute for Linux Snaps: `sudo snap install --classic jenkins`
* Otherwise, download and install it from: https://jenkins.io/download (it's available for Arch Linux, FreeBSD, Gentoo, macOS, OpenBSD, OpenIndiana Hipster, openSUSE, Red Hat/Fedora/Alma/Rocky/CentOS, Ubuntu/Debian, Windows)

NOTE: Pipelines are supported in Jenkins version 2.337 or newer.

💻 Browse to your new Jenkins server
-------------------------------------
Launch your Web browser and enter the URL: **http://HOSTNAME:8080** (replace HOSTNAME by the computer name where Jenkins has been installed).

🔓 Unlock Jenkins
-----------------
1. Execute `sudo cat /DISPLAYED/PATH/TO/initialAdminPassword` to display the initial password saved by Jenkins.
2. Enter the initial password to unlock Jenkins.

📌 Install necessary Plugins
-----------------------------
1. Click on **'Select plugins to install'**
2. Add these plugins: **'Build Name and Description Setter'**
3. Click **Install** and wait until the installation has finished.

🧙‍♂️ Create the Administrator Account
------------------------------------
1. Enter the username, password (twice), and the full name.
2. Afterward, enter your Jenkins URL and log in.
     
📝 Create a Pipeline
---------------------
1. In the dashboard click on: **+ Create element** (on left side).
2. Enter a job name (e.g. "sample-pipeline") and select **Pipeline**, then press the OK button.
3. The job configuration is displayed now - scroll down and select the **Pipeline script**.
4. As script enter the content of the **Jenkinsfile** (attached to this repository).
5. Click the **Save** button.
     
▶️ Start a Pipeline Job
------------------------
1. Click on **Dashboard** (on left side).
2. In your job list press the green **Play** button (on right side).
3. The **Stage View** visualizes the whole build process in a neat table.
  
🏆 Congratulations
-------------------
* Welcome to the Jenkins ecosystem! The following links might be useful:
* Jenkins Homepage at: https://www.jenkins.io/
* Jenkins User Documentation at: https://www.jenkins.io/doc/
* Jenkins Handbook at: https://www.jenkins.io/doc/book/
* Discover 1800+ Jenkins plugins at: https://plugins.jenkins.io/ to extend your Jenkins installation.
* Find the Jenkins app for Android devices at: https://play.google.com/store/apps/details?id=com.mobilabsolutions.jenkins.app

📧 Feedback
------------
Anything missing or is incorrect? Don't be shy, just send your email feedback to: markus.fleschutz [at] gmail.com

🤝 License & Copyright
-----------------------
This open source project is licensed under the CC0 license. All trademarks are the property of their respective owners.
