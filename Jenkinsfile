#!groovy
pipeline {
  agent any
  environment	{
    BRANCH = "${env.BRANCH_NAME}"
  }
  stages {
    stage('Build on Jenkins') {
      steps {
        sh 'npm --version'
        sh 'npm install'
        sh 'npm install now'
        sh 'ng install'
        sh 'ng run build'
      }
    }
    stage('Deploy to Zeit'){
      when {
        branch 'master'
      }
      echo "Starting deployment from master BRANCH"

      stage('Sending Build to Zeit') {
          steps {
            sh 'now'
          }
        }

    }
  }
}

def test(String n){
  echo n
}
