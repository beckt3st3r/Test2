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
            build(job: 'ParamItem1', parameters: [string(name: 'Str2', value: String.valueOf(Str2)),
                                                                                      string(name: 'Str3', value: String.valueOf(Str3)),
                                                                                      string(name: 'Str1', value: String.valueOf(Str1))])
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
          environment {
            Str2 = 'testmetonight'
          }
          steps {
            build(job: 'ParamItem2', parameters: [string(name: 'Str2', value: String.valueOf(Str2))])
          }
        }
        stage('GetResults2') {
          steps {
            junit 'testResults/junit2.xml'
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
  environment {
    Bool1 = 'true'
    Bool2 = 'false'
    Str1 = 'String1Test'
    Str2 = 'String2Test'
    Str3 = 'NOTINTESTBUTOK'
  }
}