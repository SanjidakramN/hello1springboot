@Library('sanju-slb') _
pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                mavenBuild()
		withCredentials([usernamePassword(credentialsId: 'github-id', passwordVariable: 'PASSWORD', usernameVariable: 'USERNAME')])
                sh'''
                docker build -t sanjidakram/java-image .
                docker login -u $USERNAME -p $PASSWORD
                docker push sanjidakram/java-image
                '''
            }
        }
        stage('run') {
            steps {
                sh'''
                kubectl apply -f deployment.yaml
                '''
            }
        }
    }
}
