pipeline {
  agent {
    node {
      label 'jdk8'
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
  }
  environment {
    MY_NAME = 'Mary'
    SONAR = credentials('test-user')
  }
  parameters {
    string(name: 'Name', defaultValue: 'whoever you are', description: 'Who should I say hi to?')
  }
}