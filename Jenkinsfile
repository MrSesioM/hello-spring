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
		post {
			always {
				junit 'target/surefire-reports/*.xml'
			}
		}
	stage('Deploy') {
            steps {
                sh 'docker-compose up -d'
            }
        }
    
    }
}
