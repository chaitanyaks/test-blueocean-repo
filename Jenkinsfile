pipeline {
  agent {
    node {
      label 'docker-slave-1'
    }

  }
  stages {
    stage('build') {
      steps {
        sh 'hostname'
      }
    }
    stage('test') {
      steps {
        sh 'pwd && ls'
      }
    }
  }
}