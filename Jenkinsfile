pipeline {
    agent { label 'agent-1' }
    stages {
        stage('start') {
            steps {
                configFileProvider ([configFile(fileId: 'kubeconfig', variable: 'KUBE_CONF')]) {
        sh """
          echo $KUBE_CONF > $HOME/.kube/config
          kubectl config use-context minikube
          kubectl get po
        """
        }
            }
        }
    }
}
