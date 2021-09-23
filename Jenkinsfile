pipeline {
	agent { label 'master' }
	stages {
		stage('BUILD') {
			parallel {
				stage('BUILD1') {
					steps {
						sh 'echo this is my first stage in pipeline job'
						sh 'ls -lrt'
						sh 'sleep 5'
					}
				}
				
				stage('BUILD2') {
					steps {
						sh 'echo this is my first stage in pipeline job'
						sh 'ls -lrt'
						sh 'sleep 5'
					}
				}
			}
		}	
		stage('TEST') {
			steps {
				sh ''' 
					sleep 5
					du -h 
				   '''
			}
		}
		
		stage('DEPLOY') {
			steps {
				sh ''' 
					sleep 5
					du -h 
				   '''
			}
		}
	}
}