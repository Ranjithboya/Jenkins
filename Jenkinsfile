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
    }
}
 
