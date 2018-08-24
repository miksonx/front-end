pipeline {
    agent any

    tools {
	npm 'NodeJS 4.8.6'
	}
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
		sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
		sh 'npm test'
            }
        }
        stage('Package') {
            steps {
                echo 'Deploying....'
		sh 'npm install'
		sh 'npm run package'
		archiveArtifacts artifacts: '**/distribution/*.zip', fingerprint: true
            }
        }
    }
}
