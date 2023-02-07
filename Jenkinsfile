pipeline {
    agent any

    stages {
        stage('mvnw') {
            steps {
                sh './mvnw package'
            }
                post {
                    always {
                            junit 'target/surefire-reports/*.xml'
                    }
                }
        }
        stage('Build') {
            steps {
                sh 'docker-compose build'
            }
        }
        
        stage('Deploy') {
            steps {
                sh 'docker-compose up -d'
            }
        }

    }
}
