pipeline {
    agent any
    
    parameters {
        string(name: 'BRANCH', defaultValue: 'main', description: 'Branch to build')
    }
    
    triggers {
        GenericTrigger(
            genericVariables: [
                [$class: 'GenericVariable', key: 'webhookTriggered', value: '$class']
            ],
            regexpFilterText: '',
            token: 'my-token',
            printContributedVariables: true
        )
    }
    
    stages {
        stage('Checkout') {
            steps {
                script {
                    checkout([$class: 'GitSCM',
                             branches: [[name: "*/${params.BRANCH}"]],
                             userRemoteConfigs: [[url: 'https://github.com/devops-regulus/test_api.git']]])
                }
            }
        }
        
        stage('Build') {
            steps {
                script {
                    sh 'ls'
                }
            }
        }
        
        stage('Deploy') {
            steps {
                script {
                    sh 'ls'
                }
            }
        }
    }
    
    post {
        success {
            echo 'Build successful - deploying now'
        }
        failure {
            echo 'Build failed - notify someone'
        }
    }
}
