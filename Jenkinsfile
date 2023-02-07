pipeline {
    agent any

    stages {
        stage('mvnw') {
            steps {
                sh './mvnw package'
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
