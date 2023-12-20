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

// when { changeset "dev/**" }

/*

pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                script {
                    checkout scm
                }
            }
        }

        stage('dev') {
            when {
                expression { 
                    return env.CHANGE_BRANCH == 'dev'
                }
            }
            steps {
                echo "dev branch"
            }
        }

        stage('UAT') {
            when {
                expression { 
                    return env.CHANGE_BRANCH == 'uat'
                }
            }
            steps {
                echo "uat branch"
            }
        }

    }

    post {
        success {
            echo 'Build and test successful!'
        }
        failure {
            echo 'Build or test failed.'
        }
    }
}



*/
