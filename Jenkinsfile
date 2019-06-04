pipeline {
    stages {
        stage('Building Image') {
            steps{
                script{
                    docker build src/details -t details:1.0
                }
            }
        }
    }
}