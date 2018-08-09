pipeline {
  agent {
    node {
      label 'jdk8'
    }
     libraries {
    lib("SharedLibs")
  }

  }
  stages {
    stage('build') {
      steps {
        echo "app is being built by ${params.Name}!"
        echo "${SONAR_USR}"
        echo "${SONAR_PSW}"
        sh 'java -version'
      }
    }
    
     stage('Shared Lib') {
         steps {
             helloWorld("Jenkins")
         }
      }
    stage('Deploy') {
     
      steps {
        echo "Deploying...."
      }
    }
  }
  environment {
    MY_NAME = 'Mary'
    SONAR = credentials('test-user')
  }
 
}
