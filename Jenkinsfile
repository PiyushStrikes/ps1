pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                script {
                    git branch: 'main', credentialsId: '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', url: 'https://github.com/piyushLiferay/ps1.git'
                }
                echo "checkout"
            }
        }
        stage('dev') {
             when { branch 'dev'}
            steps {
                echo 'hello world'
            }
        }
        stage('uat') {
            when { branch 'uat'}
            agent {
                docker { image 'node:16-alpine' }
            }
            steps {
                sh 'node --version'
            }
        }
    }
}





// when { branch '*/master'}

/*

*/
