pipeline {
    agent any

    stages {

        stage('Git Clone') {
            steps {
                git 'https://github.com/mhaskesarvesh1145-sudo/flask-cici-project.git'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t flaskcici:v1 .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop flask || true'
                sh 'docker rm flask || true'
                sh 'docker run -d -p 5000:5000 --name flask flaskcici:v1'
            }
        }
    }
}
