pipeline {
  agent { label 'master' }
  tools {
    maven 'MAVEN_HOME'
  }
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/Pavankumar-99/myProject'
      }
    }
    stage('Build') {
      steps {
        bat 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        bat 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        bat 'mvn package'
      }
    }
  }
}
