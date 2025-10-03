pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Application is in Building Phase'
                bat 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                echo 'Application is in Testing Phase'
                bat 'mvn test'
            }
        }
        stage('Deploy to Cloudhub') {
            environment {
                ANYPOINT_CREDENTIALS = credentials('platform.credentials')
            }
            steps {
                echo 'Deploying Application to CloudHub'
                bat 'mvn deploy -DmuleDeploy'
            }
        }
    }
}
