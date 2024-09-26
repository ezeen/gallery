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
        

        stage('Running locally'){
            steps{
                echo 'Running.......'
                sh 'nohup node server.js &'
            }
        }

        
    }
}