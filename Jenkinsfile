pipeline {
  agent {
    node {
      label 'jdk8'
    }

  }
  stages {
    stage('build') {
      steps {
        echo "app is being built by ${MY_NAME}!"
        sh 'java -version'
      }
    }
  }
  environment {
    MY_NAME = 'Mary'
  }
}