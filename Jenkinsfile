pipeline {
    agent { label 'agent-1' }
    stages {
        stage('start') {
            steps {
                script {
                kubernetesDeploy(configs: "dep.yaml", kubeconfigId: "mykubeconfig")
                }
            }
        }
    }
}
