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
        timeout(time: 1, unit:'HOURS')
        disableConcurrentBuilds()
    }
     parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
        stage('Examplechecking params') {
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
            }
        }
    }
    // post build
    post {
        always {
            echo " welcome to jenkins webhook"
        }
        failure {
            echo " this message comes after failure"
        }
        success {
            echo "this build was successfull"
        }
    }
}