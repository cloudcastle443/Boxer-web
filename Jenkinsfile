pipeline {
    agent any {
        stages {
            stage('Chekout application code') {
                steps {
                    script {
                        checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'Githubaccess', url: 'https://github.com/cloudcastle443/Boxer-web.git']])
                    }
                }
            }
        }
    }
}