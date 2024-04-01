pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Build frontend artifacts
                sh 'npm install'
                sh 'npm run build'
                // Build backend artifacts (assuming Maven)
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                // Execute unit tests for frontend and backend
                sh 'npm test'
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                // Deploy to staging environment
                sh 'ansible-playbook deploy.yml -i inventory/staging'
            }
        }
    }
}
