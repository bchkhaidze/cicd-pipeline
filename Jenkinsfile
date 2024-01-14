pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        script {
          checkout scm
          #sh scripts/build.sh
          def customImage = docker.build("${registry}:${env.Build_ID}")
        }
      }
    }


    stage('Test') {
      steps {
        script {
          docker.withRegistry('','dockerhub_id'){
            docker.image("${registry}:${env.BUILD_ID}").push('latest')
            docker.image("${registry}:${env.BUILD_ID}").push("${env.BUILD_ID}")
          }
        }

      }
    }

    stage('Publish') {
      steps {
        script {
          docker.withRegistry('','dockerhub_id'){
            docker.image("${registry}:${env.BUILD_ID}").push('latest')
            docker.image("${registry}:${env.BUILD_ID}").push("${env.BUILD_ID}")
          }
        }

      }
    }

  }
  environment {
    registry = 'bakari1991/flask_app'
  }
}