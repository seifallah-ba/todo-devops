pipeline {
    agent any
	stages {
        stage('Build') {
            steps {
				echo 'fetching code from git'
				script {
                    sh '''
                    git clone -b develop https://github.com/seifallah-ba/todo-devops.git
                    '''
                }
				echo 'fetching is done!'
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