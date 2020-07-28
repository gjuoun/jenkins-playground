pipeline {
    agent { docker 'node:14.5.0-alpine3.10' }
    environment {
        GITHUB_TOKEN     = credentials('github_token')
    }
    stages {
        stage('install') {
            steps {
                // install git
                sh 'apk add git'
                sh 'git --version'
            }
        }
        stage("update") {
            steps{
                sh 'echo "trigger a build"'
                sh 'echo "update a file" > update.txt'
                sh 'git add .'
                sh 'git commit -m "jenkins test: update a file "'
                sh 'echo $GITHUB_TOKEN'
            }
        }
    }
}

// test/once again
