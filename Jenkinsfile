pipeline {
	agent any 
	
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
				sh 'cp target/Motorola.war /home/asta/group/apache-maven-3.9.1'
				}
}
}
}

