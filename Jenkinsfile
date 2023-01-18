pipeline {
	agent none
	environment {
		DOCKER_LOGIN = credentials('docker_login')
	}

    stages {
        stage('Build on k8 ') {
            steps {           
		        sh 'ls -ltr'
                        sh 'pwd'
		        sh 'docker login -u $DOCKER_LOGIN_USR -p $DOCKER_LOGIN_PSW
		        sh '/usr/local/bin/helm upgrade --install petclinic-app helm/petclinic'
              			
            }           
        }
    }
}
