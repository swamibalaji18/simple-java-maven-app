pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /root/.m2:/root/.m2'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh ' sh \'mvn -B -DskipTests clean package\''
      }
    }
    stage('Test') {
      steps {
        sh 'sh \'mvn test\''
      }
    }
    stage('Deliver') {
      steps {
        sh 'sh \'./jenkins/scripts/deliver.sh\''
      }
    }
  }
}