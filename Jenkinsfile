pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/avi-ar/alc.git'
            }
        }
        
        stage('Copy Files') {
            steps {
                sh 'rsync -avz . /path/to/destination/'
            }
        }
        
        stage('Run Terraform') {
            steps {
                sh 'terraform init'
                sh 'terraform fmt'
                sh 'terraform plan'
                sh 'terraform apply -auto-approve'
            }
        }
    }
