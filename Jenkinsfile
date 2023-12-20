pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                script {
                    git branch: 'main', credentialsId: 'secret-text', url: 'https://github.com/piyushLiferay/ps1.git'
                }
                echo "checkout"
            }
        }
        stage('dev') {
             when { branch 'dev'}
            steps {
                echo 'dev  changes'
            }
        }
        stage('main') {
            when { branch 'main'}
            agent {
                docker { image 'node:16-alpine' }
            }
            steps {
                sh 'node --version'
            }
        }

        stage('print') {
            steps {
                echo " testing..."
            }
        }
    }
}