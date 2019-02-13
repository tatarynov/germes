pipeline {
  agent any
  environment {
    PATH = '$PATH:/usr/local/bin/'
  }
  stages {
    stage('unit test') {

      steps {
        sh '''export PATH=$PATH:/usr/local/bin/

mvn clean test'''
      }
    }
    stage('integration test') {
      steps {
        sh 'echo \'Integration tests are running\''
      }
    }
    stage('UI tests') {
      steps {
        build(job: 'Smoke_UI_Test', propagate: true, wait: true)
      }
    }
  }
}