pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url:https://github.com/tirupdev/py_gha_jen.git'
            }
        }

        stage('Install Python3 & pip') {
            steps {
                sh '''
                    sudo apt update
                    sudo apt install -y python3 python3-pip
                    python3 --version
                    pip3 --version
                '''
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'python3 -m pip install -r requirements.txt'
            }
        }

        stage('Run Script') {
            steps {
                sh 'python3 main.py' // replace with your script
            }
        }
    }
}
