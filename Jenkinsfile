pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                // Compile your Java code (e.g., javac MyJavaFile.java)
                sh 'javac my-java-app.java'
            }
        }
        stage('Run') {
            steps {
                // Execute your compiled Java code (e.g., java MyJavaFile)
                sh 'java my-java-app'
            }
        }
    }
}
