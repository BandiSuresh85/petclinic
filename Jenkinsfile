pipeline {
	agent any

    stages {
        stage('Build on k8 ') {
            steps {           
		        sh 'ls -ltr'
                        sh 'pwd'
		        sh '/usr/local/bin/helm upgrade --install petclinic-app helm/petclinic'
              			
            }           
        }
    }
}
