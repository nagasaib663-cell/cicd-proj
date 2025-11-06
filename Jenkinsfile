pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Manishb06/secure-cicd-demo.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('Checkstyle') {
            steps {
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('Gitleaks') {
            steps {
                // If Jenkins agent has Docker
                sh 'docker run --rm -v "$PWD":/path zricethezav/gitleaks:latest detect --source=/path --no-git'
            }
        }
        // Optional: add more
    }
    post {
        always {
            archiveArtifacts artifacts: '**/target/**/*', allowEmptyArchive: true
            junit 'target/surefire-reports/*.xml'
        }
    }
}
