pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/username/repository.git', credentialsId: 'github-token'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install' // Replace with your build command
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test' // Replace with your test command
            }
        }

        stage('Deploy') {
            steps {
                sh 'scp target/*.jar user@your-server:/path/to/deploy' // Example deploy command
            }
        }
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build or deployment failed.'
        }
    }
}
