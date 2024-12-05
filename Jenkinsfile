pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git url: 'https://github.com/jjeongmin98/Test.git', credentialsId: 'git_hub'
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
