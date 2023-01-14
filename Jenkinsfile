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
        sh "docker-compose down"
        sh "docker stop $(docker ps -a -q)"
        sh "docker system prune -a -f"
        sh "docker-compose up"
      }
    }
  }
}
