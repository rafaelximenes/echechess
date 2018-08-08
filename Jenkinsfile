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
        withSonarQubeEnv('teste') {
          sh 'mvn clean package sonar:sonar'
        }
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
    
