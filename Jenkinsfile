pipeline {
    agent any
    
    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/yourusername/simple-jenkins-pipeline.git'
            }
        }
        
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        
        stage('Run Tests') {
            steps {
                sh 'mvn test'
            }
        }
        
        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
    
    post {
        success {
            echo '🎉 Build and tests passed successfully!'
        }
        failure {
            echo '❌ Build or tests failed. Check the logs!'
        }
    }
}

