pipeline {
    agent { label 'master' }

    stages {
        stage('checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/id-dockerfile-create']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHubAccess', url: 'https://github.com/Octobit8-DevOps/java-pipeline.git']]])
            }
        }
        stage('compile')
        {
            steps{
                sh 'mvn clean'
                sh 'mvn compile'
                sh 'mvn package'
            }
        }
    }
}
