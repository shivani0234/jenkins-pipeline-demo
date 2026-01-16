pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/shivani0234/jenkins-pipeline-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-demo:latest .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker rm -f jenkins-demo || true
                docker run -d -p 5000:5000 --name jenkins-demo jenkins-demo:latest
                '''
            }
        }
    }
}
