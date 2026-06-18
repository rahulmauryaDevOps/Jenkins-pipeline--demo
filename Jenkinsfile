pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-demo:v1 .'
            }
        }

        stage('Remove Old Container') {
            steps {
                sh 'docker rm -f jenkins-demo || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d --name jenkins-demo -p 8081:80 jenkins-demo:v1'
            }
        }

        stage('Verify Container') {
            steps {
                sh 'docker ps'
            }
        }
    }
}