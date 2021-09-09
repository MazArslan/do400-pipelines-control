node('nodejs') {
  stage('checkout') {
    git branch: 'main', url: 'https://github.com/MazArslan/do400-pipelines-control
  }
  stage('backend test') {
    sh 'node ./backend/test.js'
  }
  stage('frontend test') {
    sh 'node ./frontend/test.js'
  }
}
