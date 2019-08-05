pipeline {
    agent {
    	docker {
    		image 'node:8'
    	}
    }
    parameters {
        choice(name:'buildType',choices:'构建\n回滚',description:'选择要执行的操作; \n发布上线/测试选择构建 \n回退版本选择回滚')
    }
    stages {
    	stage('Build') {
			steps {
				echo "${params.PerformMavenRelease}"
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