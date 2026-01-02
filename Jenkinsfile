pipeline {
    agent {
        docker {
            image 'maven:3.9.6-eclipse-temurin-17'
        }
    }

    environment {
        SLACK_WEBHOOK = credentials('slack-webhook')
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }

    post {
        success {
            sh '''
            curl -X POST -H 'Content-type: application/json' \
            --data '{"text":"✅ Pipeline SUCCESS - Projet DevOps Bouhmadi Manar"}' \
            $SLACK_WEBHOOK
            '''
        }
        failure {
            sh '''
            curl -X POST -H 'Content-type: application/json' \
            --data '{"text":"❌ Pipeline FAILED - Projet DevOps Bouhmadi Manar"}' \
            $SLACK_WEBHOOK
            '''
        }
    }
}
