pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Building Docker Image...'

                sh 'docker build -t jenkins-demo:v1 .'
            }
        }

        stage('Verify') {
            steps {
                sh 'docker images | grep jenkins-demo'
            }
        }
    }
}