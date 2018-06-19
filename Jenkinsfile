pipeline {
  agent {
    node {
      label 'docker-slave-1'
    }

  }
  stages {
    stage('scm') {
      steps {
        git(url: 'https://chaitanyaks@bitbucket.org/chaitanyaks/terraform_repo.git', branch: 'test', credentialsId: 'bit_creds_chaitu')
      }
    }
    stage('terraform Initialization') {
      steps {
        sh '''pwd && ls
terraform init
terraform plan

'''
      }
    }
    stage('terraform applying') {
      steps {
        sh 'terraform apply -auto-approve'
      }
    }
  }
}