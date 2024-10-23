pipeline {
    agent {
    node {
        label 'AGENT-1'
        
    }
}

environment { 
        Greeting = 'Hellojenkins'
    }

    options {
                timeout(time: 1, unit: 'HOURS') 
                disableConcurrentBuilds() 
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
                sh '''
                echo "We can write shell script here"
                env
                echo "$Greeting"
                // sleep 10
                '''
            }
        }
    }

    stage("Checking Parameters usage"){
        steps{
            sh '''
            echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"

            '''
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
