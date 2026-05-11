pipeline {
    agent any

    stages {

        stage('Clone Repo') {
            steps {
                git 'https://github.com/luniticmush/SayyadParvez.github.io.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t parvez-portfolio .'
            }
        }

        stage('Remove Old Container') {
            steps {
                sh 'docker rm -f parvez-container || true'
            }
        }

        stage('Run Website') {
            steps {
                sh 'docker run -d -p 80:80 --name parvez-container parvez-portfolio'
            }
        }
    }
}
