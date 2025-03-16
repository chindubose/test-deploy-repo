pipeline {
    tools {
        nodejs 'nodejs'
    }
    agent any
    
    environment {
        registry = "683489048777.dkr.ecr.us-east-2.amazonaws.com/ecr-test-repo"
    }

    stages {
        
        stage('Deploying') {
            steps{  
                script {
                        sh 'aws ecr get-login-password --region us-east-2 | docker login --username AWS --password-stdin 683489048777.dkr.ecr.us-east-2.amazonaws.com/ecr-test-repo'
                        sh 'helm upgrade first --install mychart --namespace helm-deployment'
                }
            }
        }

    }
}
