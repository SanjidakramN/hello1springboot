pipeline {
    agent any

    stages {
        stage('run') {
            steps {
                sh'''
 		kubectl delete -f service.yaml --ignore-not-found
                kubectl apply -f service.yaml
                '''
            }
        }
    }
}
