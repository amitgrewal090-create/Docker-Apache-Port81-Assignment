pipeline {
    agent any

    stages {
        stage('Test Deployment') {
            steps {
                build job: 'Push-to-Test', wait: true
            }
        }

        stage('Production Deployment') {
            steps {
                build job: 'Push-to-Prod', wait: true
            }
        }
    }
}
