pipeline {
  agent { label 'linux1' }
  tools {
    maven 'Maven 3.5'
  }
  stages {
    stage('Checkout'){
      steps {
        git 'https://github.com/VStefan01/mvnArchetype'
      }
    }
    stage('Build'){
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
}
