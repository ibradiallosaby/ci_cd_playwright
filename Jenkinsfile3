pipeline {
    agent {
        docker{
            image 'mcr.microsoft.com/playwright:v1.65.0-jammy'
            args '-u root --entrypoint='
        }
    }

    parameters {
        booleanParam(name: 'isTags', defaultValue: true, description: 'lancer avec tous les tags?')
        choice(name: 'TAG', choices: ['smoke', 'tnr', 'regression'], description: 'Choisir un tag ?')

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
                script{
                    if(params.isTags == true){
                        sh "npx playwright test"
                    }else {
                        sh "npx playwright test --grep '${params.TAG}'"
                    }
                }
            }
        }
       
       
         
    }
} 

