pipeline {
    agent {
        label 'AGENT-1'
    }

    options {
        timeout(time: 10, unit: 'MINUTES')
        disableConcurrentBuilds()
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Kiran', description: 'who should i say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: 'One\nTwo\nThree\n', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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

        stage('Print Params') {
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
            echo "this scection runs always when finish the pipeline job"
            deleteDir()
        }

        success {
            echo "this session runs when pipeline successfully completed"
        }

        failure {
            echo "this session runs when pipeline failure"
        }
    }
}