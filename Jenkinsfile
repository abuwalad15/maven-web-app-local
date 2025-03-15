pipeline {
	agent any
	
	tools{
	git 'git-2.45.0'	
        maven 'maven-3.9.9'
	    	}
	
	stages{
		stage('Checkout Code'){
			steps{
				checkout scm
				}
			}

	stage('Build'){
		steps{
		sh "mvn clean install"
		}
	}

	stage('Deployment'){
		steps{
		deploy adapters: [tomcat9(credentialsId: '3ba6446b-de39-4611-a131-f6bc1404022a', path: '', url: 'http://54.151.134.78:8080/')], contextPath: 'maven-web-app-local', war: 'target/*.war'
		
		}
	}

	}
}
