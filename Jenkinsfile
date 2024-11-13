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
                 sh """ssh -tt -o StrictHostKeyChecking=no kazami@192.168.56.2 << EOF  2>&1                           
                         hostnamectl
                         exit
                         EOF"""
                 }
            }

        }
    }
}
