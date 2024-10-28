pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
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
                echo " name is devops"                         
            }
        }
        stage ('profession') {
            steps {
                echo " profession is software engineering"
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