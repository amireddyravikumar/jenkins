pipeline {
    agent any // Runs this pipeline on any available worker/node

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running automated tests...'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying to the server...'
            }
        }
    }
}