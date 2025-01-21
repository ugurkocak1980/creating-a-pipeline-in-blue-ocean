pipeline {
  agent {
    docker {
      args '-p 3000:3000'
      image 'node:lts-alpine'
    }

  }
  stages {
      stage('Setup') {
      steps {
        // Fix npm cache directory permissions
        sh 'npm config set cache /home/ubuntu/.npm'
        sh 'mkdir -p /home/ubuntu/.npm && chown -R $(whoami) /home/ubuntu/.npm'
      }
    }
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }

  }
}