pipeline {
    agent any

    stages {
        stage('test') {
             when {
                expression {
                    BRANCH_NAME == 'dev' &&  == true
                }
            }
            steps {
                echo 'hello world'
                git 'https://github.com/piyushLiferay/ps1.git'
                
            }
        }
        stage('build') {
            agent {
                docker { image 'node:16-alpine' }
            }
            steps {
                sh 'node --version'
            }
        }
    }
}