pipeline {
  agent any
  stages {
    stage('test') {
      parallel {
        stage('test') {
          steps {
            sh 'echo \'test\''
          }
        }
        stage('build') {
          steps {
            sh 'echo \'build\''
          }
        }
      }
    }
  }
}