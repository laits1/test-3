pipeline {
  agent any

  environment {
    GIT_URL = "https://github.com/laits1/test-3.git"
  }

  stages {
    stage('Pull') {
      steps {
        git(url: "${GIT_URL}", branch: "master", changelog: true, poll: true)
      }
    }
    stage('Terraform Init') {
            steps {
                sh 'terraform init'
            }
        }
        stage('Terraform Plan') {
            steps {
                sh 'terraform plan'
            }
        }
        stage('Terraform Apply') {
            steps {
                sh 'terraform apply -auto-approve'
            }
        }
  }
}
