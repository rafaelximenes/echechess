def version = 'teste'
pipeline {
  agent any
  stages{
    stage('Init') {
      steps {
        checkout scm
        echo "Testing..."
      }
    }
    stage('Build') {
      steps {
        echo "Building..."
      }
    }
    stage('Deploy') {
      steps {
        echo "Code deployed."
      }
    }
  }
}
    
