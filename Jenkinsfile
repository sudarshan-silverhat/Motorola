pipeline {
        agent any

        stages {
                stage('Checkout') {
                        steps {
                                checkout scm
                                }}
                stage('Build') {
                        steps {
                                sh '/home/raspsberry/DevOPS/apache-maven-3.9.1/bin/mvn install'
                                }}
                stage('Deployment'){
                        steps {
                                sh 'cp target/Motorola.war /home/raspsberry/DevOPS/apache-tomcat-9.0.73/webappsc'
                                }
}
}
}
