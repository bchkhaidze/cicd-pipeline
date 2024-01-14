pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        sh 'checkout scm'
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