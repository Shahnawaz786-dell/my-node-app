pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                echo 'Code Cloned'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh 'docker stop myapp || true'
                sh 'docker rm myapp || true'
                sh 'docker run -d --name myapp -p 80:80 myapp'
            }
        }

    }
}
