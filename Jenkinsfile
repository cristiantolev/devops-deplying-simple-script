pipeline {
    agent any

    // Define parameters
    parameters {
        booleanParam(name: 'Script_One', defaultValue: true, description: 'Do you want to install application?')
        string(name: 'Install_Path', defaultValue: '', description: 'Enter the path for the backups')
        string(name: 'Application_Name', defaultValue: '', description: 'Enter the application to install')
        string(name: 'Application_Version', defaultValue: '', description: 'Enter the application version to install')
    }

    stages {
        stage('Passing values to variables') {
            steps {
                script {
                    // Passing values from params to variables
                    def Script_One = params.Script_One
                    def Install_Path = params.Install_Path
                    def Application_Name = params.Application_Name
                    def Application_Version = params.Application_Version
                }
            }
        }

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