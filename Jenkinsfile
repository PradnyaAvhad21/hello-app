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
        // Remove old container if exists
        sh 'docker rm -f hello-pradnya || true'
        // Build and run new container
        sh 'docker build -t hello-pradnya .'
        sh 'docker run -d -p 5000:5000 --name hello-pradnya hello-pradnya'
    }
}

        }
    }
