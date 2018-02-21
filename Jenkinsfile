pipeline {
  agent {
    node {
      label 'Master'
    }
    
  }
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
        sh 'python temp.py'
      }
    }
    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            echo 'Run Test'
          }
        }
        stage('Test2') {
          steps {
            echo 'In Test 2'
          }
        }
        stage('Test3') {
          steps {
            echo 'Test3'
          }
        }
      }
    }
    stage('Tests complete') {
      steps {
        echo 'Done'
        junit 'local.xml'
      }
    }
  }
  environment {
    Start = 'none'
  }
}