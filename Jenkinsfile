pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/vignesh-palanirajan/pes2ug22cs661_jenkins'
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'g++ -o main/hello_exec main/hello.cpp'
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh './main/non_existent_file' // This file does not exist, so it will fail
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline failed! Check logs for errors.'
        }
        success {
            echo 'Pipeline executed successfully!'
        }
    }
}
