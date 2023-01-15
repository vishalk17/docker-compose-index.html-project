pipeline{
  agent {
  node {
   label 'master'
   customWorkspace '/mnt/main/'
  }
  }
    stages{
        stage ("deploy index.html"){
            steps{
                sh "docker-compose down"
### check whether containers exist or not if return 0 then echo " no container found elso stop all running container one by one ###
                if [ -n "$(docker ps -a -q)" ]; then
                  docker stop $(docker ps -a -q)
                else
                echo "No container found"
                fi
###
                sh "docker system prune -a -f"
                sh "docker-compose up"
            }
        }
    }
}
