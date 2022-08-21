pipeline{

	agent any

	environment {
		DOCKERHUB_CREDENTIALS=credentials('samarHACATHONSDACODINGDOJO')
	}

	stages {

		stage('Build') {

			steps {
				sh 'docker build -t samaribrahim/hacathon:latest .'
			}
		}

		stage('Login') {

			steps {
				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}

		stage('Push') {

			steps {
				sh 'docker push samaribrahim/hacathon:latest .'
			}
		}
	}

	post {
		always {
			sh 'docker logout'
		}
	}

}