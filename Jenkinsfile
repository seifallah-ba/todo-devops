pipeline {
    agent any
	stages {
        stage('Build') {
            steps {
                echo 'git clone'
				echo 'npm install'
				echo 'npm run build'
            }
        }
        stage('Eslint Test') {
            steps {
				echo 'npm run eslint'
            }
        }
		
		stage('Unit Test') {
            steps {
				echo 'npm run test'
            }
        }
    }
}