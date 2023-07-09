pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat(script: 'cd frontend && npm install', returnStdout: true)
        bat(script: 'cd backend && npm install', returnStdout: true)
      }
    }

  }
}