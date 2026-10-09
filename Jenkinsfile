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
        stage('SonarQube Analysis') {
            steps {
                dir('backend/backend') {
                    withSonarQubeEnv('SonarQube') {
                        sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -Dsonar.projectKey=DevOps-AppGestionDesProjets'
                    }
                }
            }
        }
    }
}
