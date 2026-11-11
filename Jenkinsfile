pipeline {
    agent {
        docker{
            image 'mcr.microsoft.com/playwright:latest'
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
                sh 'npm install @playwright/test '
                sh 'npx playwright install'
            }
        }
        stage('Lancer le test') {
            steps {
                sh 'npx playwright test'
            }
        }
       
         
    }
} 

