pipeline {
	agent{
	label 'slave'
	}
	parameters {
		choice(name: 'ENVIRONMENT', choices: ['QA','UAT'], description: 'Pick Environment value')
	}
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/asta/group/apache-maven-3.9.1/bin/mvn install'
	                 }}
		stage('Deployment'){
		    steps {
			sh 'sshpass -p "devlop" scp target/Motorola.war asta@172.17.0.2:/home/asta/group/apache-tomcat-9.0.73/webapps'
			}}
		stage('Docker build'){
		    steps {
			sh 'docker build -t sudarshandocker01/pipelineimage11.1.20 .'
			}}
		stage('Docker Login'){
		    steps {
		withCredentials([string(credentialsId: 'sudarshandocker01', variable: 'Sidhu9876%$#@!Doc')]) {
			sh 'docker login -u sudarshandocker01 -p${docker-swapnilhub}'                 
			echo 'Login Completed'
			}			
			}}
		stage('Push Image to Docker Hub') {         
    		    steps{                            
 			sh 'docker push sudarshandocker01/pipelineimage11.1.20:$BUILD_NUMBER'           
			echo 'Push Image Completed'       
    			}}
		
}}
