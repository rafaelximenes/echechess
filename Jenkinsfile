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
        withSonarQubeEnv('My SonarQube Server') {
          sh 'mvn clean package sonar:sonar'
        }
      }
    }
    stage('Deploy') {
      steps {
        echo "Code deployed."
      }
    }
  }
}
    
