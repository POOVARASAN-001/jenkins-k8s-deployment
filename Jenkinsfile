
pipeline {
    agent any

    environment {
        KUBECTL = 'D:\\DockerApp\\resources\\bin\\kubectl.exe'
        KUBECONFIG = 'C:\\Users\\POOVARASAN\\.kube\\config'
    }

    stages {
        stage('Deploy Web Application') {
            steps {
                bat '"%KUBECTL%" apply -f deployment.yaml'
            }
        }

        stage('Verify Deployment') {
            steps {
                bat '"%KUBECTL%" rollout status deployment/web-deployment --timeout=120s'
                bat '"%KUBECTL%" get deployments'
                bat '"%KUBECTL%" get pods -l app=web-app'
            }
        }
    }
}
