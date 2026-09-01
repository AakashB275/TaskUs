pipeline{
    agent any
    stages{
        stage('Clone Repo'){
            steps{
                git branch: 'main', url: 'https://github.com/AakashB275/TaskUs'
            }
        }
        stage('Build image'){
            steps{
                sh 'docker build -t flas-app .'
            }
        }
        stage('Deploy with docker compose'){
            steps{
                // existing container if they are running
                sh 'docker compose || true'
                //start app, rebuild flask image
                sh 'docker compose up -d --build'
            }
        }
    }
}