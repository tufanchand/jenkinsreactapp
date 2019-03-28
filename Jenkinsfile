pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'npm install'
        echo 'NPM Packages has been loaded'
      }
    }
    stage('Test') {
      steps {
        sh 'bash ./jenkins/scripts/test.sh'
        input(message: 'are u sure to continue', ok: 'Yes')
      }
    }
    stage('Deliver and Stop') {
      steps {
        sh 'bash ./jenkins/scripts/deliver.sh'
        input(message: 'Have u tested ?', ok: 'Yes and success and Continue')
        sh 'bash ./jenkins/scripts/kill.sh'
      }
    }
  }
}