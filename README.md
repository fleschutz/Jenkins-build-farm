Sample Pipeline
===============

This repo contains a sample Pipeline for Jenkins. Required is the following:

1. **Install Jenkins v2.303.3 or newer.**
   For Linux snaps execute: `snap install --beta --classic jenkins`
   Otherwise, download and install it from: https://jenkins.io/download
2. **Launch Jenkins and browse to** http://<YOURHOSTNAME>:8080
3. **Unlock Jenkins** by entering the file content of the displayed file.
4. **Click on 'Select plugins to install' and choose the following plugins:
4. Click 'Manage Jenkins', select 'Manage Plugins' and install these plugins: 'Pipeline', 'Pipeline: Declarative', 'Pipeline: Stage View', and the 'Git client' plugin.
5. Click 'Create element', then choose 'Pipeline'.
6. Click on 'Build now'
