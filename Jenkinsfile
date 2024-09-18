pipeline {
    agent {
        node {
            label 'Ec2' 
        }
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/avi-ar/alc.git'
            }
        }
        stage('entering a') {
            steps {
                sh 'cd /alc'
            }
        }
        stage('Terraform Init') {
            steps {
                sh 'terraform init'
            }
        }
        stage('Terraform Plan') {
            steps {
                sh 'terraform plan'
            }
        }
        stage('Terraform Apply') {
            steps {
                input message: 'Apply Terraform changes?'
                sh 'terraform apply -auto-approve'
            }
        }
    }
}
