pipeline {
  agent {
    node {
      label 'jdk9'
    }

  }
  stages {
    stage('build') {
      steps {
        echo 'building my app still'
        sh 'java -version'
      }
    }
  }
}