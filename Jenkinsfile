pipeline {
  agent {
    node {
      label 'docker-slave-1'
    }

  }
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            sh 'hostname'
          }
        }
        stage('scm') {
          steps {
            git(url: 'https://chaitanyaks@bitbucket.org/chaitanyaks/terraform_repo.git', branch: 'test', credentialsId: 'bit_creds_chaitu')
          }
        }
      }
    }
    stage('test') {
      steps {
        sh '''cd /home/jenkins
pwd && ls
terraform init
terraform plan

'''
      }
    }
  }
}