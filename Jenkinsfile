#!/usr/bin/env groovy

node {
  try {
    parallel [
      test: stage('Test'){
        checkout scm
        echo 'test'
      },
      build: stage('Build Image'){
        echo "building from branch ${env.BRANCH_NAME}"
      }
    ]
    stage('after'){   
      archiveArtifacts(artifacts: 'auto/*', excludes: "auto/.gitkeep")
      echo 'after'
    }

  } catch (err) {
    echo 'alert error in build'
    archiveArtifacts(artifacts: 'automation/artifacts/*', excludes: '.gitkeep')
    throw err
  }
}
