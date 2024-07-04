pipeline {
    agent any
    
    triggers {
        GenericTrigger(
            genericVariables: [
                [$class: 'GenericVariable', key: 'webhookTriggered', value: '$class']
            ],
            token: 'test',
            printContributedVariables: true
        )
    }
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Build') {
            steps {
                sh 'echo "Building..."'
            }
        }
        
        stage('Deploy') {
            steps {
                sh 'echo "Deploying..."'
            }
        }
    }
    
    post {
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed.'
        }
    }
}
