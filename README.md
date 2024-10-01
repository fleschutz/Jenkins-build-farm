Set up a Jenkins Build Farm
===========================

This repo contains step-by-step instructions to install [Jenkins](https://jenkins.io) and sample [Pipelines](https://www.jenkins.io/doc/book/pipeline/) for CI/CD (Continuous Integration and Continuous Delivery/Deployment).

🔧 1. Install the Jenkins server
-----------------------------------
* Execute for Docker: `docker run -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts-jdk11`
* Execute for Linux Snaps: `sudo snap install --classic jenkins`
* Otherwise, download and install it from: https://jenkins.io/download (available for Arch Linux, FreeBSD, Gentoo, macOS, OpenBSD, OpenIndiana Hipster, openSUSE, Red Hat/Fedora/Alma/Rocky/CentOS, Ubuntu/Debian, Windows)
* **NOTE:** Pipelines are supported in Jenkins version 2.337 or newer.

💻 2. Browse to your new Jenkins server and unlock it
------------------------------------------------------
1. Launch your Web browser and enter the URL: **http://HOSTNAME:8080** (replace HOSTNAME by the computer name where Jenkins has been installed).
2. Execute `sudo cat /PATH/TO/initialAdminPassword` (replace /PATH/TO) to view the initial password saved by Jenkins during the installation.
3. Enter the initial password to unlock Jenkins.

📌 3. Install necessary Plugins
--------------------------------
1. Click on **'Select plugins to install'**
2. Add these plugins: **'Build Name and Description Setter'**
3. Click **Install** and wait until the installation has finished.

🧙‍♂️ 4. Create an Admin Account
------------------------------
1. Enter the username, password (twice), and the full name.
2. Afterward, enter your Jenkins URL and log in.
     
📝 5. Create a Pipeline
------------------------
1. In the dashboard click on: **+ Create element** (on left side).
2. Enter a job name (e.g. "sample-pipeline") and select **Pipeline**, then press the OK button.
3. The job configuration is displayed now - scroll down and select the **Pipeline script**.
4. As script enter the content of the **Jenkinsfile** (attached to this repository).
5. Click the **Save** button.
     
▶️ 6. Start the Pipeline Job
-----------------------------
1. Click on **Dashboard** (on left side).
2. In your job list press the green **Play** button (on right side).
3. The **Stage View** visualizes the whole build process in a neat table.
  
🏆 Congratulations
-------------------
You're done. Welcome to the Jenkins ecosystem! More background information can be found here:

* **Homepage** at: https://www.jenkins.io
* **User Documentation** at: https://www.jenkins.io/doc
* **Handbook** at: https://www.jenkins.io/doc/book

🚀 What's Next?
----------------
* **Use the Jenkins app** on your smartphone to trigger and watch builds anytime anywhere. It's available for free at: https://play.google.com/store/apps/details?id=com.mobilabsolutions.jenkins.app
* **Add more user accounts:** click *Manage Jenkins &gt; Users* to create and manage user accounts. 
* **Add more plugins:** visit the *Jenkins Plugins Index* at: https://plugins.jenkins.io and discover 1900+ plugins.
* **Add more machines** for a distributed build environment (build farm). More information at: https://www.jenkins.io/doc/book/using/using-agents
* **Add more jobs:** see the sample Pipeline scripts in subfolder 📂[examples](examples/) to build GitHub projects.
* **Back up your Jenkins:** just zip the Jenkins home folder (at: ~/.jenkins or at: /var/snap/jenkins) and copy it to another disk.

📧 Feedback
------------
Anything missing or needs to be improved? Don't be shy, just send your email feedback to: markus.fleschutz [at] gmail.com

🤝 License & Copyright
-----------------------
This open source project is licensed under the CC0 license. All trademarks are the property of their respective owners.
