pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t badekeerthi/my-image:new-tag .'
            }
        }
        stage('Push'){
            steps{
                script{
                    withDockerRegistry(credentialsId: 'docker-id') {
                        sh 'docker push badekeerthi/my-image:new-tag'
                    }
                }
            }
        }
    }
}
