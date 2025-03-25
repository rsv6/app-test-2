pipeline {
    agent any

    stages {
        stage('Update image') {
            steps {
                script {
                    sh 'docker-compose build --no-cache'
                }
            }
        }
        stage('Recreate service') {
            steps {
                script {
                    sh 'docker-compose up -d --force-recreate'
                }
            }
        }
        stage('Remove unused images') {
            steps {
                script {
                    sh 'docker image prune -f'
                }
            }
        }
    }
}