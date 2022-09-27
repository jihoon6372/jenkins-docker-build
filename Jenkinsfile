pipeline {
  stage('========== Clone repository ==========') {
    checkout scm
  }
  stage('========== Build image ==========') {
    app = docker.build("jihoon6372/jenkins-docker-build")
  }
  stage('========== Push image ==========') {
    docker.withRegistry('https://registry.hub.docker.com', 'jihoon6372') {
      app.push("${env.BUILD_NUMBER}")
      app.push("latest")
    }
  }
}