pipeline {
    agent any

    stages {
        // stage('checkout') {
        //     steps {
        //         git url: 'git@github.com:msaavedra91/jenkins-training.git'
        //     }
        // }

        stage('Set Terraform path') {
            steps {
                script {
                    def tfHome = tool name: 'Terraform'
                    env.PATH = "${tfHome}:${env.PATH}"
                }
                sh 'terraform --version'
            }
        }

        stage('Terraform Init') {
            steps {
                sh 'terraform init'
            }
        }

        stage('Terraform Plan') {
            steps {
                sh 'terraform plan -out=plan'
            }
        } 
    }
}
