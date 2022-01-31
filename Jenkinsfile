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
        stage('Use_kube_confing') {
            steps {
              script {
              withCredentials([file(credentialsId: 'newconfig', variable: 'KUBE_CONF')]) {
              sh """
                cat $KUBE_CONF > $HOME/.kube/config
                sed -i 's/afann/lts/g' dep.yaml
                kubectl apply -f  .
              """
              }
              
            }
            }
          }
    }
}
