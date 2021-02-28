pipeline {
    agent any
    
    environment {
        DOCKER_LOGIN = 'mdnfiras'
        DOCKER_PASS = credentials('dockerhub-firas-token')
    }
    
    stages {
        stage ('Angular image build') {
            steps {
                sh 'docker build --tag ${DOCKER_LOGIN}/my-angular:latest --file ./angular-app/Dockerfile ./angular-app/'
                sh 'docker login -u ${DOCKER_LOGIN} -p ${DOCKER_PASS}'
                sh 'docker push ${DOCKER_LOGIN}/my-angular:latest'
            }
        }
        stage ('Express image build') {
            steps {
                sh 'docker build --tag ${DOCKER_LOGIN}/my-express:latest --file ./express-server/Dockerfile ./express-server/'
                sh 'docker login -u ${DOCKER_LOGIN} -p ${DOCKER_PASS}'
                sh 'docker push ${DOCKER_LOGIN}/my-express:latest'
            }
        }
    }
}
