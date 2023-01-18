pipeline {
	agent any
	environment {
		Docker_login = credentials('dockerhub')
    stages {
        stage('Build on k8 ') {
            steps {           
		        sh 'ls -ltr'
                        sh 'pwd'
		        sh 'docker login -u $Docker_login_USR -p $Docker_login_PSW
		        
                        sh '/usr/local/bin/helm upgrade --install petclinic-app helm/petclinic'
              			
            }           
        }
    }
}
