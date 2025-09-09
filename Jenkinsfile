pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/anilkumarmidde09/Sample_CICD_Docker_Jenkins_EC2_Repo.git'

            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("myapp:${BUILD_NUMBER}")
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    dockerImage.run("-p 5000:5000")
                }
            }
        }
    }
}
