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

  }
}