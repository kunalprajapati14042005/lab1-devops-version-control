pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Build stage started.'
                sh 'test -f app/index.html'
                echo 'Build completed successfully.'
            }
        }

        stage('Test') {
            steps {
                echo 'Test stage started.'
                sh 'grep -q "Jenkins Deployment Successful" app/index.html'
                echo 'Test completed successfully.'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy stage started.'
                sh 'rm -rf /tmp/lab1-deployed'
                sh 'mkdir -p /tmp/lab1-deployed'
                sh 'cp -r app/* /tmp/lab1-deployed/'
                sh 'ls -la /tmp/lab1-deployed'
                echo 'Application deployed successfully.'
            }
        }
    }

    post {
        success {
            echo 'Post-build action: Deployment completed successfully.'
        }

        failure {
            echo 'Post-build action: Pipeline failed.'
        }
    }
}
