pipeline {
    agent { docker 'node:14.5.0-alpine3.10' }
    environment {
        GITHUB_TOKEN     = credentials('github_token')
    }
    stages {
        stage("environment check"){
            steps {
                sh 'echo ${JOB_NAME}-${BUILD_NUMBER}'
                sh 'echo ${BUILD_ID}'
            }
        }
        stage('install') {
            steps {
                sh 'echo install git'
            
            }
        }
        stage("update") {
            steps{
                sh 'git status'
                sh 'git add .'
                sh 'git commit -m "jenkins test: update a file "'
                sh 'echo $GITHUB_TOKEN'
                sh 'git config --global user.name "gjuoun"'
                sh 'git config --global user.email "gjuoun@gmail.com"'
                sh 'git push'
            }
        }   
    }
}

