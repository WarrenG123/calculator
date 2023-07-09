pipeline {
  agent any
  stages {
    stage('Build Frontend') {
      steps {
        bat 'cd frontend && npm install'
        bat 'cd frontend && npm run dev'
      }
    }

    stage('Build Backend') {
      steps {
        bat 'cd backend && npm install --production'
        bat 'cd backend && node app.js '
      }
    }

  }
}