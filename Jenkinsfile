pipeline {
    agent any
    
    parameters {
        string(name: 'branch', defaultValue: '', description: 'Branch name')
    }

    stages {
        stage('Build') {
            steps {
                script {
                    if (params.branch ==~ /refs\/heads\/master/) {
                        sh 'ls'
                    } else if (params.branch ==~ /refs\/heads\/test/) {
                        sh 'df -h'
                    } else {
                        echo "Branch not specified or does not match master or test"
                    }
                }
            }
        }
    }
}
