pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker build -t subbudockerlearning425/adservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker login -u subbudockerlearning -p Subbu@425"
                        sh "docker push docker.io/subbudockerlearning425/adservice:latest"
                    }
                }
            }
        }
    }
}
