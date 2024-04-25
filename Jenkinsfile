pipeline {
    agent any
    environment {
        AWS_ACCESS=credentials('Cem')
        AWS_REGION = 'us-east-1'
    }
    stages {
        stage('Create Infrastructure') {
            steps {
                dir('terraform-files') {
                    script {
                        sh(script: 'terraform init', returnStdout: true)
                        sh(script: 'terraform plan', returnStdout: true)
                        sh(script: 'terraform apply -auto-approve', returnStdout: true)
                    }
                }
            }
        }
        stage('Build Images') {
            steps {
                script {
                    sh 'echo "Images Build"'
                }
            }
        }
        stage('Push Images to ECR') {
            steps {
                script {
                    sh 'echo "Images Pushed"'
                }
            }
        }
        stage('Wait') {
            steps {
                script {
                    sh 'echo "Wait is done."'
                }
            }
        }
    }
}










