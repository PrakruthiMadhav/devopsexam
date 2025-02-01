pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building application...'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying application...'
                    // Create the deployment directory using cmd
                    bat "mkdir \"${WORKSPACE}\\pythonappdeploy\""
                    // Verify the existence of app.py
                    bat "dir ${WORKSPACE}"
                    // Copy the app.py file
                    bat "copy \"${WORKSPACE}\\app.py\" \"${WORKSPACE}\\pythonappdeploy\\\""
                }
            }
        }

        stage('Run Application') {
            steps {
                script {
                    echo 'Running application...'
                }
            }
        }

        stage('Test Application') {
            steps {
                script {
                    echo 'Testing application...'
                }
            }
        }
    }
}
