pipeline {
  agent {
    kubernetes {
      cloud 'terralogic-eks-agent'
      namespace 'cloudbees-builds'
      inheritFrom 'jenkins-kaniko-agent'
      defaultContainer 'jnlp'
    }
  }

  stages {
    stage('Install Dependencies') {
      steps {
        sh 'npm install'
      }
    }
  }
}
