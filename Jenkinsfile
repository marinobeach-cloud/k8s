pipeline {
  agent any
  tools {
    maven 'Maven 3.3.6'
  }
  stages {
    stage ('Initialize') {
      steps {
        sh '''
          echo "PATH = ${PATH}"
          echo "M2_HOME = ${M2_HOME}"
        '''
      }
    }
    stage ('Compile') {
      steps {
        sh 'mvn clean compile'
      }
    }
    stage ('Test') {
      steps {
        sh 'mvn clean test'
      }
    }
    stage ('Deploy') {
      steps {
        echo 'mvn install'
      }
    }
  }
  post {
    success {
      echo 'SUCCESSFUL pipeline'
    }
    unsuccessful {
      echo 'FAILURE pipeline'
    }
  }
}