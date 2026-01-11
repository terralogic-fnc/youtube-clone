pipeline {
  agent {
    kubernetes {
      cloud 'terralogic-eks-agent'
      namespace 'cloudbees-builds'
      inheritFrom 'jenkins-kaniko-agent'
      defaultContainer 'jnlp'
    }
  }

    stages{
        stage('Clean'){
            steps{
                 cleanWs()
            }
        }
    stage('Install Dependences'){
            steps{
                sh 'npm install'
            }
        }

    }
}
