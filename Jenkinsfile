pipeline {
    agent any  // Runs on any available agent
    
    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'g++ -o hello_exec hello.cpp'  // Compiling C++ file
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh './hello_exec'  // Executing compiled C++ file
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh 'echo "Deployment Complete"'
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
