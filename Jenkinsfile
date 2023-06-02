pipeline {
  agent any

  stages {
    // first stage installs node dependencies and Cypress binary
    stage('build image') {
      steps {
        // there a few default environment variables on Jenkins
        // on local Jenkins machine (assuming port 8080) see
        // http://localhost:8080/pipeline-syntax/globals#env
        echo "Running build ${env.BUILD_ID} on ${env.JENKINS_URL}"
        sh 'docker build -t cypress-test .'
      }
    }

    stage('start local server') {
      steps {
        // start local server in the background
        // we will shut it down in "post" command block
        sh 'docker-compose run e2e-chrome'
      }
    }

    stage('pwd') {
      steps {
        // start local server in the background
        // we will shut it down in "post" command block
        sh 'pwd'
      }
    }
  }
}
