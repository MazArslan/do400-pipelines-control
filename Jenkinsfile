pipeline {
  agent {
    node {
      label 'nodejs'
    }
  }
  stages {
    stage('run tests') {
      parallel {
        stage('backend test') {
          steps {
            sh 'node ./backend/test.js'
          }
        }
        stage('frontend test') {
          steps{
            sh 'node ./frontend/test.js'
          }
        }
      }
    }
  }
}