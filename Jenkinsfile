#!groovy
pipeline {
  agent any
  environment	{
    BRANCH = "${env.BRANCH_NAME}"
  }
  stages {
    stage('Build on Jenkins') {
      steps {
        'npm --version'
        'npm install'
        'npm install now'
        'ng install'
        'ng run build'
      }
    }
    stage('Deploy to Zeit'){
      when {
        branch 'master'
      }
      steps {
        echo "Starting deployment from master BRANCH"
        'now'
      }
    }
  }
}

def test(String n){
  echo n
}
