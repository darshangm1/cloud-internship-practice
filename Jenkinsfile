pipeline {
    agent any

    environment {
        DOCKERHUB_USERNAME = "instantprachi"
        IMAGE_NAME = "nginx-static-site"
    }

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/your-username/your-repo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKERHUB_USERNAME/$IMAGE_NAME:latest .'
            }
        }

        stage('Push Docker Image') {
            steps {
                echo 'Docker image will be pushed to Docker Hub'
                sh 'docker push $DOCKERHUB_USERNAME/$IMAGE_NAME:latest'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
