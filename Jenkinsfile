pipeline {
    agent any

    stages {
         stage('Init') {
            steps {
                sh 'sudo docker rm -f $(docker ps -qa) || true'
            }
        }
        stage('Build') {
            steps {
                sh 'sudo docker build -t myapp .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'sudo docker run -d -p 80:5500 --name myapp myapp:latest'
            }
        }
    }
}
