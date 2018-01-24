pipeline {
  agent any
  stages {
    stage('test') {
      parallel {
        stage('test') {
          steps {
            sh '''echo \'test\'
ls -al'''
          }
        }
        stage('build') {
          steps {
            sh '''echo \'build\'
ls -al .'''
          }
        }
      }
    }
  }
}