pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/jjeongmin98/Test.git'
      }
    }

    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            sh 'sudo docker-compose up --build -d --force-recreate'
          }
        }

        stage('Check_container') {
          steps {
            sh 'sudo docker ps -a'
          }
        }

      }
    }

  }
}