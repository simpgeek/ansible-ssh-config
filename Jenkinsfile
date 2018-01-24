#!/usr/bin/env groovy

node {
  try {

      parallel {

        'test': stage('Test'){
          echo 'test'
        }

        'build': stage('Build Image'){
          echo "building from branch ${env.BRANCH_NAME}"
        }
      }
      stage('after'){
        echo 'after'
      }
    

  } catch (err) {
  echo 'alert error in build'
  archiveArtifacts(artifacts: 'automation/artifacts/*', excludes: '.gitkeep')
  throw err
  }
}
