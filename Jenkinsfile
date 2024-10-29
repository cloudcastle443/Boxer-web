pipeline {
    agent any

    parameters {
        string(name: 'Docker_Image_Name', defaultValue: 'boxer', description: 'Name of the Image')
    }

    stages {
        stage('Checkout application code') {
            steps {
                script {
                    checkout([$class: 'GitSCM', branches: [[name: '*/main']], 
                             userRemoteConfigs: [[credentialsId: 'Githubaccess', 
                                                  url: 'https://github.com/cloudcastle443/Boxer-web.git']]])
                }
            }
        }
        stage('Build docker image') {
            steps {
                script {
                    // building docker image
                    sh "docker build -t ${params.Docker_Image_Name}:latest . -f Dockerfile"
                }
            }
        }
    }
}
