pipeline {
  agent {
    node {
      label 'nodejs'
    }
  }
  parameters {
    booleanParam(name: "RUN_FRONTEND_TEST", defaultValue: true)
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
          when { expression {params.RUN_FRONTEND_TEST } }
          steps{
            sh 'node ./frontend/test.js'
          }
        }
      }
    }
    stage('Deploy') {
      when {
        expression {env.GIT_BRANCH == 'origin/main'}
        beforeInput true
      }
      input {
        message 'deploy the application?'
      }
      steps {
        echo 'Deploying..'
      }
    }
  }
}