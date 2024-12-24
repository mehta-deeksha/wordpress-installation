pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                // Checkout the repository containing your Ansible files
                git branch: 'main',
                    url: 'https://github.com/mehta-deeksha/wordpress-installation.git',
                    credentialsId: 'repo-password' // Replace with your Jenkins credentials ID
            }
        }


        stage('Run Ansible Playbook') {
            steps {
                // Run the Ansible playbook for WordPress deployment
                sh '''
                ansible-playbook -i hosts wordpress.yml
                '''
            }
        }
    }

    post {
        success {
            echo 'WordPress deployment successful!'
        }
        failure {
            echo 'WordPress deployment failed!'
        }
    }
}
