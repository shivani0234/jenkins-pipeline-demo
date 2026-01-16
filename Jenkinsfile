pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-demo .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker rm -f jenkins-demo || true
                docker run -d -p 5000:5000 --name jenkins-demo jenkins-demo
                '''
            }
        }
    }
}
