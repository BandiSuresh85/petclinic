pipeline {
	agent any
	environment {
		dockerhub = credentials('dockerhub')
    stages {
        stage('Build on k8 ') {
            steps {           
		        sh 'ls -ltr'
                        sh 'pwd'
		        sh 'docker login -u $dockerhub_USR -p $dockerhub_PSW
		        
                        sh '/usr/local/bin/helm upgrade --install petclinic-app helm/petclinic'
              			
            }           
        }
    }
}
