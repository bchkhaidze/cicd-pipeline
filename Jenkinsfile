pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        script {
          checkout scm
        }
    }

    stage('Build') {
        steps {
            sh chmod 777 scripts/build.sh
            sh scripts/build.sh
        }
    }

    stage('Test') {
        steps {
            sh chmod 777 scripts/test.sh
            sh scripts/test.sh
        }
    }
    }
  }
    post {
        success {
            echo 'Pipeline succeeded!'

            // Optionally, you can perform additional actions after a successful build
        }

    failure {
      echo 'Pipeline failed!'
    }

  }
}