pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/your-repo.git'
      }
    }

    stage('Deploy') {
      steps {
        sh 'docker-compose up --build -d --force-recreate'
      }
    }

  }
}