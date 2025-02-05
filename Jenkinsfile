pipeline {
    agent any 

    stages {
	     stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Roshnithakur92/project-demo.git'
            }
        }
		
		stage('Build Docker Image') {
            steps {
                sh 'docker build -t "us-central1-docker.pkg.dev/halogen-order-447007-t3/terraform/pthonimage:latest" .'
            }
        }
        
        stage('Push to Artifact Registry') {
            steps {
		         sh 'gcloud auth configure-docker us-central1-docker.pkg.dev'
			  sh 'docker push "us-central1-docker.pkg.dev/halogen-order-447007-t3/terraform/pthonimage:latest"'
             }
         }
     }
   }
