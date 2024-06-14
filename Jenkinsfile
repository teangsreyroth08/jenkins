pipeline {
    agent any // window agent, Jenkins-laravel (other machine)
    stages {
        stage('Fetch from GitHub') { //build steps
            steps {
                echo 'Fetching for GitHub'
                git branch: 'JenkinsFinal', url: 'https://github.com/teangsreyroth08/jenkins.git'
            }
        }
        stage('Build using Tools'){
            steps{
                echo 'Compiling code ...'
                sh 'cp .env.example .env'
                sh 'composer install && php artisan key:generate && npm install && npm run build'
            }
        }
        stage('Test the app'){
            steps{
                echo 'Testing unit tests...'
                echo 'Testing feature...'
                sh 'php artisan test'
            }
        }
        
    }
    
}
