pipeline {
    agent any

    stages {
        stage ('Deploy to curretn environment') {
            steps {
                sh 'docker-compose up -d'
            }
        }
    }
}
