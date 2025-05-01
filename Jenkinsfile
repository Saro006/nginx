pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Deploy to Minikube') {
            steps {
                script {
                    sh '''
                    echo "👉 Checking current Kubernetes context..."
                    kubectl config current-context

                    echo "📂 Moving to deployment directory..."
                    cd deployment-manifest

                    echo "🚀 Applying Deployment YAML..."
                    kubectl apply -f deployment.yaml --validate=false

                    echo "🌐 Applying Service YAML..."
                    kubectl apply -f service.yaml --validate=false

                    echo "🔍 Getting pods..."
                    kubectl get pods

                    echo "✅ Deployment complete."
                    '''
                }
            }
        }
    }
}
