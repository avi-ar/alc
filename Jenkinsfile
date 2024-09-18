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
        
        stage('Terraform Init') {
            steps {
                sh 'terraform init'
                }
            }
        }
        
        stage('Terraform Plan') {
            steps {
                {
                    sh  'terraform plan'
                }
            }
        }
        
        stage('Terraform Apply') {
            steps {
                input message: 'Apply Terraform changes?'

                    sh  'terraform apply -auto-approve'
                }
            }
        }
    }
}
