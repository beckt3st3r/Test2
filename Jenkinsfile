pipeline {
  agent any
  stages {
    stage('s1') {
      parallel {
        stage('s1') {
          steps {
            echo 'a1'
          }
        }
        stage('') {
          steps {
            sh 'sh moveResults.sh'
          }
        }
      }
    }
    stage('error') {
      steps {
        junit 'testResults/junit.xml'
      }
    }
  }
}