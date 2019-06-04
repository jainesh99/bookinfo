pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build src/details -t details:1.0'
            }
        }
}
}