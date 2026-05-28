pipeline {

    agent any 

    stages {
        stage('Clone code'){
            steps {
                git branch: 'main',
                url: 'https://github.com/samidha1-1/flask-app.git'
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
