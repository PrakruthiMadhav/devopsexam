pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Installing dependencies...'
                sh 'pip install -r requirements.txt'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'python3 -m unittest discover'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh 'mkdir -p python-app-deploy && cp app.py python-app-deploy/'
            }
        }
        stage('Run Application') {
            steps {
                echo 'Running application...'
                sh 'nohup python3 python-app-deploy/app.py > app.log 2>&1 &'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check the logs.'
        }
    }
}
