pipeline {
    agent any    
    stages {
        stage('Deploy to Staging') {
            steps {
                sshagent(['jenkins_key']) {
                    sh 'ssh -o StrictHostKeyChecking=no -L $(pwd)/docker.sock:/var/run/docker.sock ubuntu@172.31.27.102 "docker run hello-world"'
                }
            }        
        }
    }
}

