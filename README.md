How to install Jenkins and a Pipeline
=====================================

This repo contains simple step-by-step instructions to install [Jenkins](https://jenkins.io) and your first sample [Pipeline](https://www.jenkins.io/doc/book/pipeline/) for CI/CD (Continuous Integration and Continuous Delivery/Deployment).

🔧 Install the Jenkins server
------------------------------
* For Snaps execute: `sudo snap install --edge --classic jenkins`
* For Docker execute: `docker run -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts-jdk11`
* Otherwise download and install it from: https://jenkins.io/download (it's available for Arch Linux, FreeBSD, Gentoo, macOS, OpenBSD, OpenIndiana Hipster, openSUSE, Red Hat/Fedora/Alma/Rocky/CentOS, Ubuntu/Debian, Windows)

NOTE: Pipeline support has been introduced in Jenkins version 2.337 or newer.

💻 Browse to your new Jenkins server
-------------------------------------
* Launch your Web browser and enter the URL: **http://HOSTNAME:8080**

NOTE: Replace HOSTNAME by the computer name where Jenkins has been installed.

🔓 Unlock Jenkins
-----------------
* Execute `sudo cat /DISPLAYED/PATH/TO/initialAdminPassword` to display the initial password saved by Jenkins.
* Enter the initial password to unlock Jenkins.

📌 Install necessary Plugins
-----------------------------
* Click on **'Select plugins to install'**
* Add these plugins: **'Build Name and Description Setter'**
* Click **Install** and wait until the installation has finished.

🧙‍♂️ Create the Administrator Account
------------------------------------
* Enter the username, password (twice), and the full name.
* Afterward, enter your Jenkins URL and log in.
     
📝 Create a Pipeline
---------------------
* In the dashboard click on: **+ Create element** (on left side).
* Enter a job name (e.g. "sample-pipeline") and select **Pipeline**, then press the OK button.
* The job configuration is displayed now - scroll down and select the **Pipeline script**.
* As script enter the content of the **Jenkinsfile** (attached to this repository).
* Click the **Save** button.
     
▶️ Start a Pipeline Job
------------------------
* Click on **Dashboard** (on left side).
* In your job list press the green **Play** button (on right side).
* The **Stage View** visualizes the whole build process in a neat table.
  
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
