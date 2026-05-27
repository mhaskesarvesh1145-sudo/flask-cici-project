pipeline {
    agent any

    stages {

        stage('Git Clone') {
            steps {
                git 'https://github.com/USERNAME/flask-cicd-project.git'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t flaskcicd:v1 .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop flaskapp || true'
                sh 'docker rm flaskapp || true'
                sh 'docker run -d -p 5000:5000 --name flaskapp flaskcicd:v1'
            }
        }
    }
}
