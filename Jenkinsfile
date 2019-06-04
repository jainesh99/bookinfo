pipeline {
node {
    stages {
        stage('Building Image') {
            steps{
                script{
                    sh 'docker build src/details -t details:1.0'
                }
            }
        }
    }
    }
}