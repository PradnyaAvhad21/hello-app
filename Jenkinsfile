pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/<username>/hello-app.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t hello-pradnya .'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker run -d -p 5000:5000 --name hello-pradnya hello-pradnya'
            }
        }
    }
}
