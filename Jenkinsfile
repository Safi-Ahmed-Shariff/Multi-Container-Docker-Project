pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Building frontend and backend images
                    sh 'docker-compose build'
                }
            }
        }
        stage('Run') {
            steps {
                script {
                    // Starting the containers
                    sh 'docker-compose up -d'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Add any tests if necessary
                    echo 'Running tests...'
                }
            }
        }
    }
    post {
        always {
            script {
                // Cleanup
                sh 'docker-compose down'
            }
        }
    }
}