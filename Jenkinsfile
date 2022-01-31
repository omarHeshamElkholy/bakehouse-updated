pipeline {
    agent { label 'agent-1' }
    stages {
        stage('start') {
            steps {
                configFileProvider ([configFile(fileId: 'kubeconfig', variable: 'KUBE_CONF')]) {
        sh """
          kubectl config --kubeconfig=$kubeconfig view
          kubectl get pods --kubeconfig=$kubeconfig
        """
        }
            }
        }
    }
}
