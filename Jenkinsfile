pipeline {
  agent {
    node {
      label 'nodejs'
    }
  }
  stages {
    stage('backend tests') {
      steps {
        sh 'node ./backend/test.js'
      }
    }
    stage('frontend test') {
      steps{
        sh 'node./frontend/test.js'
      }
    }
  }
}