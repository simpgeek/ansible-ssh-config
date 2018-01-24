#!/usr/bin/env groovy

node {
  try {
    def steps = [:]
    steps['test'] = {
        checkout scm
        echo 'test'
    }
    steps['build'] = {
        echo "building from branch ${env.BRANCH_NAME}"
        exit 1
    }
    parallel steps
     
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
