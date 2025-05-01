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
                    cd deployment-manifest
                    kubectl apply -f deployment.yaml
                    kubectl apply -f service.yaml
                    kubectl get pods
                    '''
                }
            }
        }
    }
}
