pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build and Test') {
            steps {
                sh 'javac Main.java'
                sh 'java Main'
            }
        }
        stage('Dockerize') {
            steps {
                sh 'docker build -t my-java-app .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                withCredentials([usernamePassword(my_java_app: 'docker-hub-credentials', my_java_app: 'DOCKER_USERNAME', AbdullahNTG: 'DOCKER_PASSWORD')]) {
                    sh 'docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD'
                    sh 'docker tag my-java-app my-java-app/my-java-app:latest'
                    sh 'docker push my-java-app/my-java-app:latest'
                }
            }
        }
    }
}
