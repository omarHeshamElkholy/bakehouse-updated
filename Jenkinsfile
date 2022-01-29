pipeline {
    agent { label 'agent-1' }
    stages {
        stage('start') {
            steps {
                echo "test successfull"
                withCredentials([usernamePassword(credentialsId: 'dockerhub-creds', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD' )]) {
                    sh """
                    docker login --username ${USERNAME} --password ${PASSWORD}
                    docker build -t omarelkholy/jenapp .
                    docker push omarelkholy/jenapp
                """
                }
            }
        }
    }
}
