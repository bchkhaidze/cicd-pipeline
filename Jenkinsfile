pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh scripts/build.sh
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

            // Optionally, you can perform additional actions after a failed build
        }
    }
}
