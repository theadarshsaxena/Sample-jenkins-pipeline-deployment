pipeline {
  agent any
  stages {
    stage('Checkout') {
      parallel {
        stage('Checkout') {
          steps {
            git(url: 'https://github.com/theadarshsaxena/Sample-jenkins-pipeline-deployment/', branch: 'master')
          }
        }

        stage('PWD') {
          steps {
            sh 'pwd'
          }
        }

      }
    }

    stage('Deployment') {
      steps {
        sh 'docker run -dit --name my-apache-app -p 80:80 -v "$PWD":/usr/local/apache2/htdocs/ httpd:2.4'
        sh 'sudo chmod 666 /var/run/docker.sock'
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