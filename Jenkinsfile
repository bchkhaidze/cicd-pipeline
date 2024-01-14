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

  }
  post {
    success {
      echo 'Pipeline succeeded!'
    }

    failure {
      echo 'Pipeline failed!'
    }

  }
}