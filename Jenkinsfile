pipeline {
    agent { label 'agent-1' }
    stages {
         stage('export_serivce_acc') {
            steps {
              script {
              withCredentials([file(credentialsId: 'svc-account', variable: 'SERVICE_ACC')]) {
                sh """
                export GOOGLE_APPLICATION_CREDENTIALS=$SERVICE_ACC
                """
              }
              
            }
            }
          }
        stage('start') {
            steps {
                script {
          kubernetesDeploy(configs: "dep.yaml", kubeconfigId: "mykubeconfig")
        }
                }
        }
    }
}
