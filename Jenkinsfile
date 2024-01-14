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

		stage('Docker Image Build and Publish') {
			steps {
				script {
					docker.withRegistry('', 'hub_id'){ 
            def customImage = docker.build("${registry}:${env.BUILD_ID}")
            customImage.push()
          }
				}
			}
    }
	}

	environment {
    registry = 'bakari1991/nodeapp'
  }
}