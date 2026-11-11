pipeline {
    agent {
        docker{
            image 'mcr.microsoft.com/playwright:v1.65.0-jammy'
            args '-u root --entrypoint='
        }
    }

    stages {
         stage('Check version nodejs') {
            steps {
                sh 'npm --version'
            }
        }
        stage('installation dependances') {
            steps {
                sh 'npm install'

            }
        }
        stage('Lancer le test') {
            steps {
                sh 'npx playwright test'
            }
        }
       
         
    }
} 

