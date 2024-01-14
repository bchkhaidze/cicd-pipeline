pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        sh 'scm checkout'
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