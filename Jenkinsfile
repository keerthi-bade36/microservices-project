pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'my-eks', contextName: '', credentialsId: 'secret-id', namespace: 'my-project', serverUrl: 'https://4B78F851DDE3547C9CD470824C8195FA.gr7.us-east-1.eks.amazonaws.com']]) {
                    sh "kubectl apply -f deployment-service.yml"
                    
                }
            }
        }
        
        stage('verify Deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'my-eks', contextName: '', credentialsId: 'secret-id', namespace: 'my-project', serverUrl: 'https://4B78F851DDE3547C9CD470824C8195FA.gr7.us-east-1.eks.amazonaws.com']]) {
                    sh "kubectl get svc -n my-project"
                }
            }
        }
    }
}
