pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment {
        greeting = 'hi goodmorning'
    }
    options {
        timeout(time: 1, unit:'SECONDS')
        disableconcurrentbuilds()
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
                    sleep 10               
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