pipeline {
    agent {
        label 'AGENT-1'
    }

    options {
        timeout(time: 10, unit: 'MINUTES')
        disableConcurrentBuilds()
    }

    parameters {
        string(name: 'DEPLOY_ENV', defaultValue: 'staging', description: '')
        text(name: 'DEPLOY_TEXT', defaultValue: 'One\nTwo\nThree\n', description: '')
        booleanParam(name: 'DEBUG_BUILD', defaultValue: true, description: '')
        choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: '')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'A secret password')
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

        stage('Print Params')
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
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
