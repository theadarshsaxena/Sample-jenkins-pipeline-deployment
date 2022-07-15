pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git(url: 'https://github.com/theadarshsaxena/Sample-jenkins-pipeline-deployment/tree/master', branch: 'master')
      }
    }

    stage('Deployment') {
      steps {
        sh 'sudo cp -rvf index.html /var/www/html'
        sh 'sudo restart httpd'
      }
    }

    stage('Testing') {
      steps {
        echo 'Change this with testing script according to the app/service.'
      }
    }

    stage('Success Message') {
      steps {
        echo 'Pipeline completion succeeded'
      }
    }

  }
}