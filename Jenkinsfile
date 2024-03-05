pipeline {
    agent any 
    stages {
      stage('Clone Repository') {
        steps {
          checkout([$class: 'GitSCM',
          branches: [[name: '*/main']],
          userRemoteConfigs: [[url: 'https://github.com/Vibgang/PES2UG21CS601_Jenkins.git']]])
        }
      }

      stage('Build') {
        steps {
          buildabc 'PES2UG21CS601-1'
          sh 'g++ hello.cpp -o output'
        }
      }

      stage('Test') {
        steps {
          sh './output'
        }
      }

      stage('Deploy') {
        steps {
          echo 'deploy'
        }
      }
    }
    post {
      failure {
        error 'Pipeline failed'
      }
    }
}
  
