pipeline {
    agent any
    
    stages {
    	stage('Build') {
			steps {
				checkout scm
  				echo "current branch: $BRANCH_NAME"
				sh 'git branch'
				echo 'Build'
				echo pwd()
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