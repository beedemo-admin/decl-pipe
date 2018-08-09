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
    
    stage('Testing') {
        parallel {
          stage('Java 8') {
            agent { label 'jdk9' }
            steps {
              container('maven8') {
                sh 'mvn -v'
              }
            }
          }
          stage('Java 9') {
            agent { label 'jdk8' }
            steps {
              container('maven9') {       // has to exist in the Pod template (defined in Kubernetes cloud config in OC
                sh 'mvn -v'
              }
            }
          }
        }
      }
    stage('Deploy') {
     
      steps {
        echo "Deploying ${APP_VERSION}."
      }
    }
  }
  environment {
    MY_NAME = 'Mary'
    SONAR = credentials('test-user')
  }
 
}
