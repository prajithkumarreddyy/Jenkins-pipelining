pipeline {
    agent any

    environment {
        VENV = "venv"
    }

    stages {
        stage('Clone GitHub Repo') {
            steps {
                git branch: 'main', credentialsId: 'github-https', url: 'https://github.com/prajithkumarreddyy/Jenkins-pipelining.git'
            }
        }

        stage('Set Up Python Virtual Environment') {
            steps {
                bat 'C:\\Users\\praji\\AppData\\Local\\Microsoft\\WindowsApps\\python.exe -m venv venv'
                bat '.\\venv\\Scripts\\python.exe -m pip install --upgrade pip'
                bat '.\\venv\\Scripts\\pip install -r requirements.txt'
            }
        }

        stage('Run Flask App') {
            steps {
                bat '.\\venv\\Scripts\\python app.py'
            }
        }
    }
}

