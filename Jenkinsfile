pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Only if this is from Git
                checkout scm
            }
        }

        stage('Deploy to Minikube') {
            steps {
                script {
                    sh '''
                    echo "Applying Kubernetes YAML to Minikube..."
                    kubectl apply -f deployment-manifest
                    kubectl get pods
                    '''
                }
            }
        }
    }
}
