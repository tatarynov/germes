pipeline {
  agent any
  environment {
    PATH = "/usr/local/bin:$PATH"
  }
  stages {
    stage('unit test') {
      steps {
          sh 'mvn clean test'
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