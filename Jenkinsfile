pipeline {
    agent {
        docker {
            image 'node:8' 
            args '-p 3000:3000' 
        }
    }
    stages {
    	stage('Build') {
			setps {
				echo 'Build'
			}
    	}
    	stage('Deploy Test') {
			when {
				branch 'dev'
			}
			steps {
				echo 'delopy test'
				echo pwd()
			}
    	}
        stage('Deploy Prod') {
        	when {
        		branch 'master'
        	}
            steps {
                sh 'node -v'
            }
        }
    }
}