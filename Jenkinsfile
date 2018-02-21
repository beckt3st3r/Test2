pipeline {
  agent none
  stages {
    stage('Build') {
      steps {
        sleep 5
        echo 'In Build'
      }
    }
    stage('Deploy') {
      steps {
        echo 'In Deploy'
      }
    }
    stage('Test') {
      steps {
        echo 'Run Test'
      }
    }
  }
  environment {
    Start = 'none'
  }
}