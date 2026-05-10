pipeline {
    agent any

    environment {
        IMAGE_NAME = "shahnawaz1malik/myapp"
    }

    stages {

        stage('Clone') {
            steps {
                echo 'Code Cloned'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker push $IMAGE_NAME'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker stop myapp || true'
                sh 'docker rm myapp || true'
                sh 'docker run -d --name myapp -p 80:80 $IMAGE_NAME'
            }
        }

    }
}
