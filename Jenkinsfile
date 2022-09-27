// pipeline {
// 	agent any
// 	stages {
// 		stage('========== Clone repository ==========') {
//             checkout scm
//         }
// 		stage('========== Build image ==========') {
//             app = docker.build("jihoon6372/jenkins-docker-build")
//         }
// 		stage('========== Push image ==========') {
//             docker.withRegistry('https://registry.hub.docker.com', 'jihoon6372') {
//                 app.push("${env.BUILD_NUMBER}")
//                 app.push("latest")
//             }
//         }
// 	}
// }

// pipeline {
//     agent any
    
//     stages() {
//         stage('========== Clone repository ==========') {
//             steps() {
//                 checkout scm
//             }
//         }
        
//         stage('========== Build image ==========') {
//             steps {
//                 // app = docker.build("jihoon6372/jenkins-docker-build")
//                 sh "docker build -t jihoon6372/jenkins-docker-build ."
//                 docker.build("jihoon6372/jenkins-docker-build")
//             }
//         }
        
//         stage('========== Push image ==========') {
//             steps {
//                 // echo env.DOCKER_HUB_ACCESS_TOKEN
//                 // sh "docker push jihoon6372/jenkins-docker-build"
//                 sh "docker login -u ${DOCKER_USER_ID} -p ${DOCKER_ACCESS_TOKEN}"
//                 sh "docker push ${DOCKER_USER_ID}/jenkins-docker-build"
//             }
//         }        
//     }
// }

node {
  stage('========== Clone repository ==========') {
    checkout scm
  }
  stage('========== Build image ==========') {
    app = docker.build("jihoon6372/jenkins-docker-build")
  }
  stage('========== Push image ==========') {
    docker.withRegistry('https://registry.hub.docker.com', '6db2a1e3-0dec-49b2-96b0-a383a63585dc') {
      app.push("${env.BUILD_NUMBER}")
      app.push("latest")
    }
  }
}