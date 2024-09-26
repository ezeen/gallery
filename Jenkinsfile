pipeline{
    agent any

    tools {
        nodejs "nodeJS"
    }

    stages{
        stage('Clone Repo') {
            steps {
                git branch: 'master', url: 'https://github.com/ezeen/gallery'
            }
        }
        
        stage('Install Dependencies') {
            steps {
                echo 'Installing npm dependencies...'
                sh 'npm install'
            }
        }
        
        stage('Deploy'){
            steps{
                withCredentials([usernameColonPassword(credentialsId: '32005260-4b41-4472-a50a-c9fe113215e5', variable: 'HEROKU_CREDENTIALS')]) {
                   sh 'git push https://${HEROKU_CREDENTIALS}@git.heroku.com/jenkins-ip1.git master' }

            }
        }

        
    }
}