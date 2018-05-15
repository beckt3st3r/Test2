pipeline {
  agent any
    environment {
    Bool1 = 'true'
    Bool2 = 'false'
    Str1 = 'String1Test'
    Str2 = 'String2Test'
  }
  stages {
    stage('s1') {
      parallel {
        stage('s1') {
          steps {
            echo 'a1'
          }
        }
        stage('Move Results') {
          steps {
            sh 'sh moveResults.sh'
          }
        }
        stage('Param1') {
          environment {
            Str2 = 'NOTGOOD'
          }
          steps {
            build(job: 'ParamItem1', parameters: [string(name: 'Str2', value: String.valueOf(Str2))])
          }
        }
      }
    }
    stage('Second') {
      parallel {
        stage('getResults') {
          steps {
            junit 'testResults/junit.xml'
          }
        }
        stage('Param2') {
          steps {
            build 'ParamItem2'
          }
        }
      }
    }
    stage('finish') {
      steps {
        echo 'this'
      }
    }
  }
}
