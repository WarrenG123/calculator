pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            bat(script: 'cd frontend && npm install', returnStdout: true)
            bat(script: 'cd backend && npm install', returnStdout: true)
          }
        }

        stage('docker run') {
          steps {
            bat(returnStdout: true, script: 'cd backend && docker run --publish  3000:3000 --detach calculator ')
          }
        }

      }
    }

  }
}