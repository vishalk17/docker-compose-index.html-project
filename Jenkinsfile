pipeline {
    agent {
        node {
            label 'master'
            customWorkspace '/mnt/main/'
        }
    }
    stages {
        stage("deploy index.html") {
            steps {
                sh "docker-compose down"
                script {
                    if (sh(script: "docker ps -a -q", returnStdout: true).trim().length() > 0) {
                        sh "docker stop '\$(docker ps -a -q)'"
                    } else {
                        echo "No container found"
                    }
                }
                sh "docker system prune -a -f"
                sh "docker-compose up"
            }
        }
    }
}
