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
        echo "${SONAR_USR}"
        echo "${SONAR_PSW}"
        sh 'java -version'
      }
    }
  }
  environment {
    MY_NAME = 'Mary'
    SONAR = credentials('sonar')
  }
}