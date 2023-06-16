pipeline {
    agent any
    stages {
        stage("Stage 1"){
            steps {
                sh "sh clean.sh"
            }
        }
        stage("Stage 2"){
            steps {
                sh 'docker stop nodejs-project || true'
                sh 'docker rm nodejs-project || true'
            }
        }
        stage("Stage 3"){
            steps {
                sh 'docker build -t nodejs-project .'
            }
        }
        stage("Stage 4"){
            steps {
                sh 'docker run -p 80:5000 --name nodejs-project -d nodejs-project .'
            }
        }
    }
}