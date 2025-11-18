pipeline{
    agent any

    tools {
        maven 'Maven-3.9.11'
    }
    environment {
        DOCKER_TAG = getVersion()
    }

    stages{
        stage('SCM Checkout'){
            steps{
                git branch: 'main', credentialsId: 'gitCreds', url: 'https://github.com/noman-akram29/Jave-Application-CICD-using-Jenkins-Ansible-and-Docker.git'
            }
        }
        stage('Maven Build'){
            steps{
                sh "mvn clean package"
            }
        }
        stage('Docker Image Build'){
            steps{
                sh "docker build . -t nomanakram29/test-java-application:${DOCKER_TAG}"
            }
        }
    }

}
def getVersion(){
   def commitHash = sh label: 'Get latest commit', returnStdout: true, script: 'git rev-parse --short HEAD'
   return commitHash
}