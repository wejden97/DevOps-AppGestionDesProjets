pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Maven') {
            steps {
                dir('backend/backend') {
                    sh 'mvn compile'
                }
            }
        }
    }
}
