node {
  stage('Build') {
    checkout scm
    app = docker.build("jihoon6372/jenkins-docker-build")
  }
  stage('Deploy') {
    docker.withRegistry('https://registry.hub.docker.com', '6db2a1e3-0dec-49b2-96b0-a383a63585dc') {
      app.push("${env.BUILD_NUMBER}")
      app.push("latest")
    }
  }
}