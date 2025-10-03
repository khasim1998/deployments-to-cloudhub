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
            steps {
                echo 'Deploying Application to CloudHub 2.0'
                bat 'mvn clean deploy -DmuleDeploy'
            }
        }
    }
}

