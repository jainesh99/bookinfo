def label = "worker-${UUID.randomUUID().toString()}"

podTemplate(label: label, containers: [
  containerTemplate(name: 'docker', image: 'docker', command: 'cat', ttyEnabled: true),
  containerTemplate(name: 'kubectl', image: 'lachlanevenson/k8s-kubectl:v1.8.8', command: 'cat', ttyEnabled: true),
],
volumes: [
  hostPathVolume(mountPath: '/var/run/docker.sock', hostPath: '/var/run/docker.sock')
]) {
  node(label) {
    def harborHostName = "ec2-18-202-213-146.eu-west-1.compute.amazonaws.com"
    def project = "details"
    def containerName = "detailscontainer"
    def version = "1.0"

    stage('Create Docker images') {
      container('docker') {
          sh "docker build src/details -t ${containerName}:${version}"
          sh "docker tag ${containerName}:${version} ${harborHostName}/${project}/${containerName}:${version}"
          sh "docker push docker push ${containerName}:${version} ${harborHostName}/${project}/${containerName}:${version}"
        }
      }

    stage('Run kubectl') {
      container('kubectl') {
        sh "kubectl version"
      }
    }
  }
}