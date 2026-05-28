pipeline {

    agent any 

    stages {
        stage('Clone code'){
            steps {
                git ''
            }
        }

        stage("Install dependencies") {
            steps {
                echo "Installing dependencies"
                sh 'pip install -r requirements.txt'
            
            }
        }

        stage('Build docker image'){
            steps {
                sh 'docker build -t flask-app:latest .'
            }

        }

        stage('Run docker container') {
            steps {
                sh 'docker run -d -p 5000:5000 flask-app:latest'
            }
        }
    }
}