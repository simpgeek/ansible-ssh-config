#!/usr/bin/env groovy

node {
  try {

    steps('dunno'){
      parallel('test build'){

        stage('Test'){
          echo 'test'
        }

        stage('Build Image'){
          echo "building from branch ${env.BRANCH_NAME}"
        }
      }
      stage('after'){
        echo 'after'
      }
    }

  } catch (err) {
  echo 'alert error in build'
  archiveArtifacts(artifacts: 'automation/artifacts/*', excludes: '.gitkeep')
  throw err
  }
}
