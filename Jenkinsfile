pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'echo \'Building environment....\''
      }
    }
    stage('Browser Tests') {
      parallel {
        stage('Safari') {
          steps {
            sh 'echo \'executing system tests on safari....\''
          }
        }
        stage('Chrome') {
          steps {
            sh 'echo \'executing system tests on chrome...\''
          }
        }
        stage('Firefox') {
          steps {
            sh 'echo \'executing system tests on firefox...\''
          }
        }
      }
    }
    stage('Beta/QA Tests') {
      steps {
        sh 'echo \'executing BETA/QA testing....\''
      }
    }
    stage('Go/No Go') {
      steps {
        input 'Finished using the web site? (Click "Proceed" to continue)'
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo \'Deployment successful\''
      }
    }
  }
}