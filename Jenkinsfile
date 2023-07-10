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
            bat(returnStdout: true, script: 'cd backend && docker run --publish  3100:3100 --detach calculatorbackend ')
          }
        }

        stage('docker frontend') {
          steps {
            bat(script: 'cd frontend && docker run --publish 3200:3200 --detach calculatorfrontend ', returnStdout: true)
          }
        }

      }
    }

  }
}