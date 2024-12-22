pipeline {
    agent any
    environment {
        ANSIBLE_HOST_KEY_CHECKING = 'False'  // Avoid host key confirmation prompts
    }
    stages {
        stage('Checkout Code') {
            steps {
                // Clone the repository containing the playbook and inventory file
                checkout scm
            }
        }
        stage('Install Dependencies') {
            steps {
                // Ensure Ansible is installed
                sh 'sudo apt-get update && sudo apt-get install -y ansible'
            }
        }
        stage('Run Ansible Playbook') {
            steps {
                ansiblePlaybook(
                    playbook: 'wordpress.yml',          // Path to your playbook
                    inventory: 'hosts',                // Inventory file
                    credentialsId: 'ssh-key-credentials-id', // Replace with Jenkins SSH credentials ID
                    colorized: true
                )
            }
        }
    }
    post {
        success {
            echo 'Deployment Successful!'
        }
        failure {
            echo 'Deployment Failed.'
        }
    }
}
