pipeline {
    agent any

    stages {
        stage('Checkout SCM') {
            steps {
                git branch: 'main',
                    url: 'https://gitea.com/shady_yasser/simple-jenkins-pipeline2.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }
    }
}

