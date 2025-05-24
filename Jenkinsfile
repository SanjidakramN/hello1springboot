pipeline {
    agent any

    stages {
        stage('run') {
            steps {
                sh'''
                kubectl apply -f service.yaml
                '''
            }
        }
    }
}
