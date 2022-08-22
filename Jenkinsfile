pipeline {
    agent { label 'local-windows-agent' }

    stages {
        stage('checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/id-dockerfile-create']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHubAccess', url: 'https://github.com/Octobit8-DevOps/java-pipeline.git']]])
            }
        }
        stage('compile')
        {
            steps{
                bat 'mvn clean'
                bat 'mvn compile'
                bat 'mvn package'
            }
        }
    }
}
