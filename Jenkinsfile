pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build stage completed successfully.'
            }
        }

        stage('Test') {
            steps {
                echo 'Test stage completed successfully.'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy stage completed successfully.'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully.'
        }
    }
}
