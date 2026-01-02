pipeline {
    agent {
        label "AGENT-1"
    }
    environment {
        COURSE = "jenkins"
    }
    stages {
        stage ("Build") {
            steps {
                script {
                    sh """
                        echo "Building..."
                                            
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