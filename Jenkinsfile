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
		deploy adapters: [tomcat9(credentialsId: 'a52389b4-4d66-4db2-a23d-08159d4ecf60', path: '', url: 'http://localhost:8080/')], contextPath: 'maven-web-app-local2', war: 'target/*.war'
		
		}
	}

	}
}
