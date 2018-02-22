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
      }
    }
    stage('Deploy to Zeit'){
      when {
        branch 'master'
      }
      steps {
        echo "Starting deployment from master BRANCH"
        sh 'now'
      }
    }
  }
}

def test(String n){
  echo n
}
