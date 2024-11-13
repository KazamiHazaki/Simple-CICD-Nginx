pipeline {
    agent any
    stages {
        stage('Test Echo') {
            steps {
                echo 'Hello, this is a test pipeline!'
            }
        }
        stage('Test Echo 2') {
            steps {
                echo 'Hello, this is a test pipeline! Step 2'
            }
        }
        stage('Try SSH') {
            steps {
                sshagent(['ssh-to-vm']) {
                 sh """ssh -tt -o StrictHostKeyChecking=no sinergimp@172.16.1.128 << EOF  2>&1                           
                         hostnamectl
                         exit
                         EOF"""
                 }
            }

        }
    }
}
