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
                sh 'job url: ${JOB_URL}'
            }
        }
        stage('install') {
            steps {
                // install git
                sh 'apk add git'
                sh 'git --version'
            }
        }
        stage("update") {
            steps{
                checkout scm
                sh 'echo "update a file" > update.txt'
                sh 'git add .'
                sh 'git commit -m "jenkins test: update a file "'
                sh 'echo $GITHUB_TOKEN'
            }
        }
        stage("push changes"){
            steps{
                sh 'git config --global user.name "gjuoun"'
                sh 'git config --global user.email "gjuoun@gmail.com"'
                sh 'git push -u origin master'
            }
        }
    }
}

