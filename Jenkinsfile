pipeline {
    agent { docker 'node:14.5.0-alpine3.10' }
    stages {
        stage('build') {
            steps {
                sh 'npm --version'
                sh '''
                  echo "Multiline shell steps works too"
                  ls -lah
                '''
                // install git
                sh 'apk add git'
                sh 'git --help'
            }
        }
    }
}

// test/again
