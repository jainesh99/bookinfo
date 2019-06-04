pipeline {
  agent any
  stages {
    stage('Build Docker Image') {
        container('docker') {
            sh "docker -v"
        }
    }
  }
}