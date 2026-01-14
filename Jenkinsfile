pipeline {
  agent any

  stages {
    stage('Stop old Container') {
      steps {
        bat 'docker rm -f day3 || exit 0'
      }
    }

    stage('Checkout Code') {
      steps {
        echo 'Pulling code from Github'
        git branch: 'main', url: 'https://github.com/your-account/your-repo.git'
      }
    }

    stage('Build Docker Image') {
      steps {
        echo 'Building Docker Image'
        bat 'docker build -t day3 .'
      }
    }

    stage('Run docker container') {
      steps {
        echo 'Running Docker container'
        bat 'docker run -d -p 8070:80 day3'
      }
    }
  }
}
