pipeline {
    agent any
    stages {
        stage('Pull Repository') {
            steps {
                 sh """ssh -tt -o StrictHostKeyChecking=no kazami@192.168.56.2 << EOF  2>&1                           
                         cd ~/Simple-CICD-Nginx
                         git pull origin main
                         exit
                         EOF"""
            }
        }
  
    }
}
