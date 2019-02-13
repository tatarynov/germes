pipeline {
  agent any
  stages {
    stage('unit test') {
      environment {
        PATH+EXTRA='/usr/local/bin/'
      }
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