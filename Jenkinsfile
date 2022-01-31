pipeline {
    agent { label 'agent-1' }
    stages {
        stage('start') {
            steps {
                configFileProvider ([configFile(fileId: 'kubeconfig', variable: 'KUBE_CONF')]) {
        sh """
          kubectl config --kubeconfig=$KUBE_CONF view
          kubectl get pods --kubeconfig=$KUBE_CONF
        """
        }
            }
        }
    }
}
