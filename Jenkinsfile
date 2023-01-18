pipeline {
  agent any
     

    tools {
      maven 'maven3'
      jdk 'JDK8'
    }
    environment {
		dockerhub = credentials('dockerhub')
	}
    stages {      
        stage('checkout ') {
            steps { 
                git 'https://github.com/BandiSuresh85/petclinic.git'
            }
        }

        stage('updating the cluster with helm charts configurations') {
            steps {
            
                sh '/usr/local/bin/helm upgrade --install petclinic-app petclinic '

            }
	}
        stage('pulling the code from dockerhub and run as a pod by using helmchart') {
            steps {
                sh 'docker login -u $dockerhub_usr -p $dockerhub_psw '

                sh '/usr/local/bin/helm upgrade --install petclinic-app petclinic --set.image.repository=registry.hub.docker.com/suresh195/petclinic --set.image.tag=1'
            }
        }
        }
        
    }  

         
     
}
