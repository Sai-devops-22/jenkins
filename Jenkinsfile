pipeline {
    agent {
        label "AGENT-1"
    }
    environment {
        COURSE = "jenkins"
    }
    options {
        timeout(time: 30, unit: "MINUTES")
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
        stage ("Build") {
            steps {
                script {
                    sh """
                        echo "Building..."
                        env
                        echo "Hello ${params.PERSON}"
                    """
                }
            }
        }
        stage ("Testing") {
            steps {
                echo "Testing..."
            }
        }
        stage ("Deploy") {   
            steps {
                echo "Deploying...."
            }
        }
    }

    post {
        always {
            echo "hello from always"
            deleteDir()
        }

        success {
            echo "hello from success"
        }

        failure {
            echo "hello from failure"
        }
    }   
}