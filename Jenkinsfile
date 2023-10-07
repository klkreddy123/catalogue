pipeline {
    agent { node { label 'AGENT-1' } }
    stages {
        stage('Install dependencies') {
            steps { 
                sh 'npm install'
            }
        }
        stage('Unit Test') {
            steps {
                echo 'Unit testing is done here'
                echo 'Unit testing is verifying here'
            }
        }
    }
}