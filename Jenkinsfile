pipeline {
    agent any
    triggers {
        GenericTrigger(
            genericVariables: [
                [key: 'ref', value: '$.ref'],
            ],
            causeString: 'Triggered on $ref',
            printContributedVariables: true,
            printPostContent: true,
            regexpFilterExpression: '',
            regexpFilterText: ''
        )
    }
    stages {
        stage('Build') {
            steps {
                echo "Building branch $ref"
            }
        }
        stage('Test') {
            steps {
                echo "Running tests for commit $after"
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying application"
            }
        }
    }
}
