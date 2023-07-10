pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'cd frontend && npm install'
            sh 'cd backend && npm install'
          }
        }

        stage('docker run') {
          steps {
            sh 'cd backend && docker run --publish  3100:3100 --detach calculatorbackend '
          }
        }

        stage('docker frontend') {
          steps {
            sh 'cd frontend && docker run --publish 3200:3200 --detach calculatorfrontend '
          }
        }

      }
    }

  }
}