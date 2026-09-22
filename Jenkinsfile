pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package -DskipTests'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t azizamri/timesheet-backend:1.0 .'
            }
        }

        stage('Docker Push') {
            steps {
                sh 'docker push azizamri/timesheet-backend:1.0'
            }
        }
    }
}
