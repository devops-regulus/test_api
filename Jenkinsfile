pipeline {
    agent any
    
    parameters {
        string(name: 'branch', defaultValue: 'master', description: 'Branch name to build')
    }
    
    stages {
        stage('Checkout') {
            steps {
                script {
                    // Checkout the specific branch
                    checkout([$class: 'GitSCM', branches: [[name: "*/${params.branch}"]], userRemoteConfigs: [[url: 'YOUR_GIT_REPO_URL']]])
                }
            }
        }
        
        stage('Build') {
            steps {
                // Replace with your build steps
                echo "Building branch: ${params.branch}"
                sh 'mvn clean package' // Example build step
            }
        }
        
        stage('Print Branch Info') {
            steps {
                script {
                    // Print branch information
                    echo "Triggered by branch: ${params.branch}"
                }
            }
        }
    }
    
    post {
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
