pipeline {
    agent {
        docker { image 'docker:latest' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'docker -v'
            }
        }
    }
}