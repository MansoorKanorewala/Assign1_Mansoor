pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                bat 'npm install -g http-server'
                timeout(time: 60, unit: 'SECONDS') {
                    bat 'http-server &'
                }
            }
        }
        
        stage('Stop') {
            steps {
                bat 'kill $(lsof -t -i:8080)'
            }
        }
    }
}

