pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "gabeshhite33/devops-project1"
    }

    stages {

        stage('Checkout Code') {
            steps {
                git 'https://github.com/ganeshhite/devops-project1.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE:latest .'
            }
        }

        stage('Push Docker Image') {
            steps {
                withDockerRegistry([credentialsId: 'dockerhub-cred', url: 'https://index.docker.io/v1/']) {
                sh 'docker push gabeshhite33/devops-project1:latest'                
                }
            }
        }

    }
}
