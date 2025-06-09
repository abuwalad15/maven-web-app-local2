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

	stage('Build War File'){
		steps{
		sh "mvn clean package"
		}
	}

	stage('Deploy ke Tomcat'){
		steps{
		deploy adapters: [tomcat9(credentialsId: '3ba6446b-de39-4611-a131-f6bc1404022a', path: '', url: 'http://54.151.248.43:8080/')], contextPath: 'maven-web-app-local2', war: 'target/*.war'
			
		}
	}

	}
}
