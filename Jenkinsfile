pipeline {
  agent any

  environment {
    NAME = "gitops-demo"
    VERSION = "1.0.0"
    IMAGE_REPO = "siddharth67"
  }
  
  stages {
    stage('Unit Tests') {
      steps {
        echo 'Implement unit tests if applicable.'
        echo 'This stage is a sample placeholder'
      }
    }

    stage('Build Image') {
      steps {
            sh "docker build -t ${NAME} ."
            sh "docker tag ${NAME}:latest ${IMAGE_REPO}/${NAME}:${VERSION}"
        }
      }

    stage('Push Image') {
      steps {
        withDockerRegistry([credentialsId: "docker-hub", url: ""]) {
          sh 'docker push ${IMAGE_REPO}/${NAME}:${VERSION}'
        }
      }
    }
  }
}
