pipeline {
    agent any
    stages {
        stage('git') {
            steps {
            git branch: 'main',
                   url: 'https://github.com/maheshryali/saleor.git'
           }
        }
        stage('docker') {
            steps {
            sh """
            docker image build -t saleor:1.0 .
            docker container run -d saleor:1.0 
            docker tag saleor:1.0 maheshryali/newimage:1.0
            docker push maheshryali/newimage:1.0
            """
            }
        }
    }
}
