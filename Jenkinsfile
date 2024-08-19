pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    def mvnHome = tool name: 'M3', type: 'maven'
                    sh "${mvnHome}/bin/mvn clean install"
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    kubernetesDeploy(configs: 'deployment.yml')
                }
            }
        }
    }
}
