pipeline {
    agent none
    stages {
        stage('Build Docker Image') {
            agent {docker 'docker:stable'}
            steps {
                echo 'Inside Docker container'
                sh 'docker -v'
            }
        }
    }
}