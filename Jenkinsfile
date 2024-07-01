pipeline {
    agent any

    stages {
        stage('Checkout repo') {
            steps {
                git 'https://github.com/cristiantolev/devops-deplying-simple-script.git'
            }
        }

        stage('Apply terraform configuration') {
            steps {
                sh 'terraform init'
                sh 'terraform apply -auto-approve'
            }
        }
    }
}