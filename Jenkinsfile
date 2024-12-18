pipeline {
    agent {
        label 'AGENT-1'
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo this is Build stage'
            }
        }
        stage('Test') {
            steps {
                sh 'echo this is Test stage'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo this is deployment stage'
            }
        }
    }
    post {
        always {
            echo "this scection rils always"
            deleteDir()
        }

        success {
            echo "this session runs when pipeline succesd"
        }

        failure {
            echo "this session runs when pipeline failurer"
        }
    }
}