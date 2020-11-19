pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn compile'
      }
    }

    stage('Unit test') {
      steps {
        sh 'mvn clean test'
      }
    }

    stage('Package') {
      steps {
        sh 'mvn package -DskipTests'
        archiveArtifacts 'target/*.war'
      }
    }

  }
  tools {
    maven 'Maven 3.6.3'
  }
}