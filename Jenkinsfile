pipeline {
    agent { 
        node {
            label 'docker-agent-python'
            }
      }
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building2.."
                sh '''
                cd myapp
                pip install -r requirements.txt
                uname -a
                whoami
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing2.."
                sh '''
                cd myapp
                python3 hello.py
                python3 hello.py --name=Huhu
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver2....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}
