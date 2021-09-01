pipeline {
  agent { label 'linux' }
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
        sh 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
  }
}
