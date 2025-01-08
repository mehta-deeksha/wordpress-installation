this repo contains a jenkinsfile (pipeline), ansible playbook wordpress.yml , hosts file and wp-config

Jenkinfile contains the pipeline script that runs in jenkins to run ansible playbook

worpdpress.yml installs and configures wordpress and its related dependencies like httpd service and php.

hosts file contains about the server information where it needs to run the playbook.


Steps to use this code:

Create a pipeline in jenkins,  copy jenkinsfile code from this repo and paste it in pipeline script section and run the job
