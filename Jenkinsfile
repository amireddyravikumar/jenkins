/* groovylint-disable-next-line CompileStatic */
pipeline {
    agent {
        node {
            label 'ROBOSHOP'
        }
    } // Runs this pipeline on any available worker/node
    environment {
        COURSE = "Jenkins"
    }
    options {
        disableConcurrentBuilds()
        timeout(time:10, unit:'MINUTES')
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'DEPLOY', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage('Build') {
            steps {
                script {
                    
                    sh """
                        echo 'Building the application...'
                        echo "course is $COURSE"
                        echo "Hello ${params.PERSON}"
                        echo "Biography: ${params.BIOGRAPHY}"
                        echo "Toggle: ${params.DEPLOY}"
                        echo "Choice: ${params.CHOICE}"
                        echo "Password: ${params.PASSWORD}" 
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
            when {
                expression { "${params.DEPLOY}" == "true"}
            }
            //  input {
            //         message "Should we continue?"
            //         ok "Yes, we should."
            //         submitter "alice,bob"
            //         parameters {
            //             string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
            //         }
            //     }
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
