pipeline{
    agent any
    stages {
        stage("Checkout") {
            steps{
                checkout scm
            }

        stage("Deploy"){
            steps{
                withCredentials([file(credentialId: 'minikube-cretentia',variable: 'KUBECONFIG')]){
                script{
                    sh '''
                    echo "Deployment

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
    }
}























// pipeline {
//     agent any

//     stages {
//         stage('Checkout') {
//             steps {
//                 checkout scm
//             }
//         }

//         stage('Deploy to Minikube') {
//             steps {
//                 script {
//                     sh '''
//                     echo "Applying Kubernetes YAML to Minikube..."
//                     cd deployment-manifest
//                     kubectl apply -f deployment.yaml
//                     kubectl apply -f service.yaml
//                     kubectl get pods
//                     '''
//                 }
//             }
//         }
//     }
// }


// #########################################
// // scripted
// node{
//     stage("Dev Stage"){
//         sh "date"
//     }

//     stage("Test Stage"){
//         sh "pwd"
//     }

//     stage("Prod Stage"){
//         sh "uptime"
//     }
// }

// // declerative


// pipeline {
//     agent any
//     stages {
//         stage ("Dev Stage"){
//              steps {
//                 sh "date"
//             }
//         }

//         stage ("Test Stage"){
//             steps{
//                 sh "pwd"
//             }
//         }

//         stage ("Prod Stage"){
//             steps {
//                 sh "uptime"
//             }
//         }
//     }
// }


// // Error handling


// pipeline {
//     agent any 
    
//     stages {
//         stage ("print stage") {
//             steps{
//                 echo 'hello world'
//             }
//             }
//         }


//     post {
//         always {
//             // any name
//             echo ' i wil always run'

//         }

//         sucess {
//             // 
//             echo ' success'

//         }

//         failure {
//             //
//             echo "failure"

//         }
//     }
// }