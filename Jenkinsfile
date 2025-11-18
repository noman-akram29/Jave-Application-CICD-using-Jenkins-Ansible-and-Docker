pipeline{
    agent any

    tools {
        maven 'Maven-3.9.11'
    }

    stages{
        stage('SCM Checkout'){
            steps{
                git branch: 'main', credentialsId: 'gitCreds', url: 'https://github.com/noman-akram29/Jave-Application-CICD-using-Jenkins-Ansible-and-Docker.git'
            }
        }
        stage('Mven Build'){
            steps{
                sh "mvn clean package"
            }
        }
    }

}