pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment {
        greeting = 'hi goodmorning'
    }
    //build
    stages {
        stage ('hi') {
            steps {
                echo " hi hello welcome"
            }
        }
        stage ('name') {
            steps {
                echo " name is devops $greeting"                         
            }
        }
        stage ('profession') {
            steps {
                sh """
                    echo " profession is software engineering"
                    lsblk
                    top
                """
            }
        }
    }
    // post build
    post {
        always {
            echo " welcome to jenkins"
        }
        failure {
            echo " this message comes after failure"
        }
        success {
            echo "this build was successfull"
        }
    }
}