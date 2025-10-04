pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Install Dependencies') {
            steps {
                bat 'pip install pytest'
            }
        }
        stage('Run Tests') {
            steps {
                bat 'pytest'
            }
        }
        stage('Package App'){
            steps{
                bat 'powershell Compress-Archive -Path * -DestinationPath build.zip'
            }
        }
        stage('Archive Zip'){
            steps{
                archiveArtifacts artifacts: 'build.zip', fingerprint: true
            }
        }
    }
}
 
