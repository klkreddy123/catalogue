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
        //sonar-scanner command expect sonar-project.properties should be available
        stage('Sonar Scan') {
            steps {
                sh 'ls -ltr'
                sh 'sonar-scanner'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deployment"
            }
        }
    }
}