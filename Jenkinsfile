pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'echo Building application...'
                sh 'docker build -t myapp .'
            }
        }

        stage('Run') {
            steps {
                sh 'docker rm -f $(docker ps -aq) || true'
                sh 'docker run -d -p 80:80 myapp'
            }
        }
    }
}
