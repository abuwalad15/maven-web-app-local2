pipeline {
	agent any
	
	tools{
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
		deploy adapters: [tomcat9(credentialsId: 'tomcat-credential', path: '', url: 'http://localhost:8080/')], contextPath: 'maven-web-app-local2', war: 'target/*.war'
		
		}
	}

	}
}
