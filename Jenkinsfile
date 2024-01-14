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
            script {
                sh scripts/build.sh
            }
        }
    }

    stage('Test') {
        steps {
            script {
                sh scripts/test.sh
            }
        }
    }
    }
}


