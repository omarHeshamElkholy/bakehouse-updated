pipeline {
    agent { label 'agent-1' }
    stages {
        stage('start') {
            steps {
                script {
                withCredentials([file(credentialsId: 'newconfig', variable: 'kubeconfig')]) {
      sh 'kubectl get pods --kubeconfig=$kubeconfig'
    }
                }
            }
        }
    }
}
