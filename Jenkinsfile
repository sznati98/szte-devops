pipeline {
    agent any
    stages {
        stage("Git clone"){
            steps {
                dir ('szte-devops') {
                    deleteDir()
                }
                script {
                    bat 'git clone https://github.com/sznati98/szte-devops.git'
                }
            }
        }
        stage('Deploy Docker image') {
            steps {
                script {
                   bat "docker stack deploy -c szte-devops/docker-compose.yml linuxserver_firefox"
                }
            }
        }
    }
}