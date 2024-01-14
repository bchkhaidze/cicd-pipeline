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
                sh chmod 777 scripts/build.sh
                sh scripts/build.sh
            }
        }
    }

    stage('Test') {
        steps {
            script {
                sh chmod 777 scripts/test.sh
                sh scripts/test.sh
            }
        }
    }
    }
}


