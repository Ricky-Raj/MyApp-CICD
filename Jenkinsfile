pipeline {
    agent any

    environment {
        IMAGE_NAME = "myapp-image"
        CONTAINER_NAME = "myapp-container"
    }

    stages {
        stage('Build') {
            steps {
                echo '📦 Building Docker image...'
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Test') {
            steps {
                echo '🧪 Running tests...'
                sh 'echo "No tests yet, skipping."'
            }
        }

        stage('Deploy') {
            steps {
                echo '🚀 Deploying the app...'
                sh '''
                    docker stop $CONTAINER_NAME || true
                    docker rm $CONTAINER_NAME || true
                    docker run -d -p 5000:5000 --name $CONTAINER_NAME $IMAGE_NAME
                '''
            }
        }
    }
}
