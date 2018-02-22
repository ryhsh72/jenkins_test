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
      steps {
        echo "Starting deployment from master BRANCH"
        sh 'npm start'
      }
    }
  }
}

def test(String n){
  echo n
}
