pipeline {
  agent any

  stages {
    stage("Check if docker is already install"){
      steps {
        sh "docker info"
      }
    }

    stage("Docker build") {
      steps {
        echo "Running test"
        sh "docker build -t jenkins-lavaravel ."
      }
    }

    stage("Run test") {
      steps {
        sh "docker run jenkins-lavaravel ./vendor/bin/phpunit tests"
      }
    }
  }
}