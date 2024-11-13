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
                    sh '''
                        [ -d ~/.ssh ] || mkdir ~/.ssh && chmod 0700 ~/.ssh
                        ssh-keyscan -t rsa,dsa example.com >> ~/.ssh/known_hosts
                        ssh kazami@192.168.56.2
                        hostnamectl
                        exit
                    '''
                 }
            }

        }
    }
}
