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
        // stage('Sonar Scan') {
        //     steps {
        //         sh 'ls -ltr'
        //         sh 'sonar-scanner'
        //     }
        // }
        // stage('Deploy') {
        //     steps {
        //         echo "Deployment"
        //     }
        // }
    stage("Build") {
        steps {
            sh 'ls -ltr'
            sh 'zip -r catalogue.zip ./* --exclude=.git --exclude=.zip'
        }
    }
    stage("Publish Artifact") {
        steps {
        nexusArtifactUploader(
            nexusVersion: 'nexus3',
            protocol: 'http',
            nexusUrl: '3.239.230.240:8081/',
            groupId: 'com.roboshop',
            version: 1.0.0,
            repository: 'catalogue',
            credentialsId: 'nexus-auth',
            artifacts: [
                [artifactId: catalogue,
                classifier: '',
                file: 'catalogue.zip',
                type: 'jar']
            ]
     )
        }
    }
    
    }
    post {
        always{
            echo 'cleaning  up workspace'
            deleteDir()
        }
    }
    
}