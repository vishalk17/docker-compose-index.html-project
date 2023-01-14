pipeline{
  agent {
  node {
   label 'master'
   customWorkspace '/mnt/main/'
  }
  }
  stages {
    stage ("deploy index.html"){
      steps{
        sh "docker-compose up"
      }
    }
  }
}
