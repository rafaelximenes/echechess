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
        withSonarQubeEnv('teste-sonar') {
          sh "mvn -Duser.language=pt -Duser.country=BR -Duser.timezone=America/Sao_Paulo -Dsonar.host.url=http://sonar.nuvem.gov.br -Dsonar.projectKey=projeto1 -Dsonar.projectName=projeto12 -Dsonar.projectVersion=1.0 -Dsonar.java.coveragePlugin=jacoco -Dsonar.dynamicAnalysis=reuseReports -Dsonar.jacoco.reportPaths=target/jacoco.exec,target/jacoco-it.exec sonar:sonar
          sh 'mvn clean package sonar:sonar -e'
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
    
