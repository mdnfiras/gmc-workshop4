pipeline {
    agent any
    
    environment {
        DOCKER_LOGIN = 'mdnfiras'
        DOCKER_PASS = credentials('dockerhub-firas-token')
    }
    
    stages {
        stage ('Angular image build') {
            steps {
                sh 'docker build --tag my-angular:latest --file ./angular-app/Dockerfile ./angular-app/'
                sh 'docker login -u ${DOCKER_LOGIN} -p ${DOCKER_PASS}'
                sh 'docker push my-angular:latest'
            }
        }
    }
}
