pipeline {
  agent any
  stages {
    stage('s1') {
      steps {
        echo 'a1'
      }
    }
    stage('error') {
      steps {
        junit 'junit.xml'
      }
    }
  }
}