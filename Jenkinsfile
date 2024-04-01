pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Clone repository
                git 'https://github.com/ujjwal2206/simple-web-application.git'
                // Copy HTML file to artifact directory
                sh 'cp index.html artifacts/'
            }
        }
        stage('Test') {
            steps {
                // Add script to check HTML validity
                sh 'html-validator index.html'
            }
        }
        stage('Deploy') {
            steps {
                // Example: Deploy to staging server using Ansible
                ansiblePlaybook playbook: 'deploy.yml', inventory: 'inventory.ini'
            }
        }
    }
}
