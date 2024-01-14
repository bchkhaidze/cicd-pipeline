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

        stage('Test') {
            steps {
                sh scripts/test.sh
            }
        }

        stage('Build Docker Image') {
            steps {
                // Build Docker image using Dockerfile
                script {
                    def customImage = docker.build("your-dockerhub-username/your-image-name:${env.BUILD_ID}")
                }
            }
        }

        stage('Publish to DockerHub') {
            steps {
                // Publish the Docker image to DockerHub
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub-credentials-id') {
                        customImage.push()
                    }
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

            // Optionally, you can perform additional actions after a failed build
        }
    }
}
