pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git branch: 'main',
            url: 'https://github.com/jjeongmin98/Test.git',
            credentialsId: 'jjeongmin98'
      }
    }
    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            sh 'docker-compose up --build -d --force-recreate'
          }
        }
        stage('Check_container') {
          steps {
            sh 'docker ps -a'
          }
        }
      }
    }
  }
}
