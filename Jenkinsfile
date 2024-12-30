pipeline {
    agent any
	stages {
        stage('Fetch') {
            steps {
				echo 'fetching code from git'
				script {
                    sh '''
					rm -rf todo-devops/*
                    git clone -b develop https://github.com/seifallah-ba/todo-devops.git
                    '''
                }
				echo 'fetching is done!'
				echo 'npm install'
				echo 'npm run build'
            }
        }
		 stage('Build') {
            steps {
				echo 'Hold on, I am installing your packages...'
				script {
                    sh '''
					cd todo-devops/frontend
                    npm install
					npm run build
                    '''
                }
				echo 'Finally, Installed and Built'
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