pipeline {
  agent {
    kubernetes {
      cloud 'terralogic-eks-agent'
      namespace 'cloudbees-builds'
      inheritFrom 'jenkins-kaniko-agent'
      defaultContainer 'jnlp'
    }
  }

  environment {
    IMAGE_NAME = "gkamalakar1006/youtubeclone"
    CI_IMAGE_TAG = "${env.BUILD_NUMBER}"
  }

  stages {


    stage('Install Dependencies') {
      steps {
        sh 'npm install'
      }
    }

    stage('Kaniko Build & Push (CI Image)') {
      steps {
        container('kaniko') {
          sh '''
            /kaniko/executor \
              --context $WORKSPACE \
              --dockerfile Dockerfile \
              --destination ${IMAGE_NAME}:${CI_IMAGE_TAG}
          '''
        }
      }
    }
  }
}
