pipeline {
    agent {
    node {
        label 'AGENT-1'
        
    }
}
    stages {
        stage('Build') {
            steps {
                echo "Hi"
            }
        }
        stage('Test') {
            steps {
                echo "Hello"
            }
        }
        stage('Deploy') {
            steps {
                echo "Namaste"
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }

        success { 
            echo 'The Job has ran successfully!'
        }

        failure { 
            echo 'Useful when alerts has to send upon failure'
        }
    }
}
