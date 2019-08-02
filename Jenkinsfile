pipeline {
    agent any
    
    stages {
    	stage('Build') {
			steps {
				sh 'git branch -a'
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
    	stage('Deploy En Test') {
    		when {
				branch 'dev'
			}
			steps {
				echo 'delopy en test'
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
        stage('Deploy En Prod') {
        	when {
        		branch 'master'
        	}
        	steps {
        		echo 'delopy en Prod'
        	}
        }
        stage('Svae Build File') {
        	when {
        		branch 'master'
        	}
        	steps {
        		echo 'Svae Build File'
        	}
        }
    }
}