pipeline {
    agent any    
    stages {
        stage('Deploy to Staging') {
            steps {
                sshagent(credentials: ['jenkins_key']) {
                sh '''
                    export DOCKER_HOST=$(pwd)/docker.sock
                    ssh -L $(pwd)/docker.sock:/var/run/docker.sock ubuntu@172.31.27.102 "docker run hello-world"
                '''
                }
            }        
        }
    }
}

