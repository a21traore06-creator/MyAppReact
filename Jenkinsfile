pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Recuperation du projet'
                checkout scm
            }
        }

        stage('Validation Docker Compose') {
            steps {
                echo 'Verification du fichier Docker Compose'
                sh 'docker compose config'
            }
        }

        stage('Build Docker Images') {
            steps {
                echo 'Construction des images Docker'
                sh 'docker compose build'
            }
        }

        stage('Run Application') {
            steps {
                echo 'Demarrage de l application'
                sh 'docker compose up -d'
            }
        }
    }

    post {
        always {
            echo 'Fin du pipeline Jenkins'
        }
    }
}