pipeline {
    agent {
        node {
            label 'ROBOSHOP'
        }
    } // Runs this pipeline on any available worker/node
    environment {
        COURSE = "Jenkins"
    }
    stages {
        stage('Build') {
            steps {
                script {
                    sh """
                        echo 'Building the application...'
                        echo "course is $COURSE"
                    """
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh """
                        echo 'Running automated tests...'
                    """
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    sh """
                       echo 'Deploying to the server...'
                    """
                }
            }
        }
    }
    //  post Build
    post {
        always {
            echo 'i will always say Hello'
        }
        success {
            echo 'i will run on success say Hello'
        }
        failure {
            echo 'i will run on failure'
        }
    }
}
