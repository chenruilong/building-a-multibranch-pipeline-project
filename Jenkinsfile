pipeline {
    agent {
        docker {
            image 'node:8' 
            args '-p 3000:3000' 
        }
    }
    stages {
    	stage('Build') {
    		checkout scm
    	}
    	stage('Deploy Test') {
			when {
				branch 'dev'
			}
			steps {
				echo 'delopy test'
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