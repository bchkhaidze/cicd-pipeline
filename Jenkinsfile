pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        script {
          checkout scm
        }

      }
    }

    stage('Build') {
      steps {
        sh '''chmod 777 scripts/build.sh
scripts/build.sh'''
      }
    }

    stage('Test') {
      steps {
        sh '''chmod 777 scripts/test.sh
scripts/test.sh'''
      }
    }
        
        
    stage('Build Docker Image') {
    	steps {
      // Build Docker image using Dockerfile
      	script {
          docker build -t nodeapp  
        }
      }
  	}

		stage('Docker Image Push') {
			steps {
				script {
					docker.withRegistry('', 'hub_id')
          { 
            app.push("${env.BUILD_NUMBER}") 
            app.push("latest") 
          }
				}
			}
    }




	}
	environment {
    registry = 'bakari1991/nodeapp'
  }
}