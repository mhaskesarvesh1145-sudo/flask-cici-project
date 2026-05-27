pipeline {
	agent any 
	stages {
		stage('Git Clone') {
			steps {
				git 'https://github.com/mhaskesarvesh-sudo/flask-cici-project.git'

				
}
		}
		stage('Docekr Build') {
			steps {
				sh 'docker built -t flaskcici:v1 .'

	}	
	}
		stage('Run Conatainer') {
			steps {
				sh 'docker stop flask || true'
				sh 'docker rm flask || true'
				sh 'docker run -d -p 5000:5000 --name flaskapp flaskcici:v1'

	}
	}
}
}
