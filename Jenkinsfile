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
        stage('error') {
          steps {
            sh 'sh moveResults.sh'
          }
        }
        stage('sleep') {
          steps {
            sh 'sleep 180'
          }
        }
      }
    }
    stage('error') {
      parallel {
        stage('error') {
          steps {
            junit 'testResults/junit.xml'
          }
        }
        stage('print me') {
          steps {
            sh 'echo printed'
          }
        }
      }
    }
    stage('sleep 3') {
      steps {
        sh 'sleep 200'
      }
    }
    stage('finish') {
      steps {
        echo 'this'
      }
    }
  }
}