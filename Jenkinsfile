def version = 'teste'
pipeline {
  agent any
  tools {
     maven 'localMaven'
  }
  stages{
    stage('Checkout') {
      steps {
        checkout scm
        echo "Testing..."
      }
    }
    stage('Test') {
      steps {
        sh "mvn clean verify package"
      }
    }
    stage('Deploy') {
      steps {
        echo "Code deployed."
      }
    }
  }
}
    