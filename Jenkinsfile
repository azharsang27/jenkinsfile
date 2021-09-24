pipeline {
	agent { label 'c-slave' }
	parameters {
		string(name: 'NAME', description: 'Enter your name here')
		text(name: 'DESCRIPTION', description: 'Enter your details here')
		booleanParam(name: 'BOOL', description: 'Enter your yes/no here')
		choice(name: 'CHOOSE BRANCH', choices: ['main','feature','hotfix'], description: 'Enter branch to build')
		choice(name: 'DENV', choices: ['TEST','QA','PROD'], description: 'Enter environment to deploy')
		password(name: 'SERVER_PWD', description: 'Enter your server password here')
	}
	stages {
		stage('BUILD') {
			parallel {
				stage('BUILD1') {
					steps {
						sh 'echo this is my first stage in pipeline job'
						sh 'ls -lrt'
						sh 'sleep 5'
						echo "NAME ${params.NAME}"
						sh "echo ${params.NAME}"
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
				if (DENV.equals(TEST)){
					"echo TEST ENV DEPLOY"
				} 
				else if (DENV.equals(QA)){
					"echo QA ENV DEPLOY"
				} 
				else if (DENV.equals(PROD)){
					"echo PROD ENV DEPLOY"
				} 
				'''
			}
		}
	} 
}