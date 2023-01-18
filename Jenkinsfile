pipeline {
  agent any
     

    tools {
      maven 'maven3'
      jdk 'JDK8'
    }
    environment {
		dockerhub = credentials('docker_login')
	}
    stages {      
        stage('checkout ') {
            steps { 
                git 'https://github.com/BandiSuresh85/petclinic.git'
            }
        }

        stage('updating the cluster with helm charts configurations') {
            steps {
            
                sh '/usr/local/bin/helm upgrade --install petclinic-app helm/petclinic '

            }
	}
        stage('pulling the code from dockerhub and run as a pod by using helmchart') {
            steps {
                sh 'docker login -u $dockerhub_USR -p $dockerhub_PSW'

                sh '/usr/local/bin/helm upgrade --install petclinic-app helm/petclinic --set image.repository=registry.hub.docker.com/suresh195/petclinic --set image.tag=1'
            }
        }
        }
        
    }  

         
     

