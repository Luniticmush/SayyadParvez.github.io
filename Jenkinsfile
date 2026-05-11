pipeline {
    agent any

    stages {

        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/luniticmush/SayyadParvez.github.io.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t parvez-portfolio .'
            }
        }

        stage('Remove Old Container') {
            steps {
                bat 'docker rm -f parvez-container || exit 0'
            }
        }

        stage('Run Website') {
            steps {
                bat 'docker run -d -p 80:80 --name parvez-container parvez-portfolio'
            }
        }
    }
}
