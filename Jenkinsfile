pipeline {

    agent any

    stages {

        stage('Build Docker Image') {

            steps {

                bat 'docker build -t devops-project .'

            }
        }

        stage('Stop Old Container') {

            steps {

                bat 'docker stop devops-container || exit 0'
                bat 'docker rm devops-container || exit 0'

            }
        }

        stage('Run Docker Container') {

            steps {

                bat 'docker run -d -p 3000:80 --name devops-container devops-project'

            }
        }
    }
}