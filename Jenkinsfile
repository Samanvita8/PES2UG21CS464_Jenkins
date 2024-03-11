pipeline {
  agent any

  stages {
    stage('Clone repository') {
        steps{
            checkout([$class: 'GitSCM',
            branches: [[name: '*/main']],
            userRemoteConfigs: [[url: 'https://github.com/Samanvita8/PES2UG21CS464_Jenkins.git']]])
        }
    }
    stage('Build') {
        steps{
            build 'PES2UG21CS464-1'
            sh 'g++ main.cpp -o output'
        }
    }
    stage('Test') {
        steps {
            sh './output' // Presumably running the compiled executable
        }
      
    }
    stage('Deploy') {
        steps {
             echo 'deploy' // Placeholder echo statement
        }
    }
    post {
      failure {
        echo 'Pipeline failed'
      }
    }
  }
}
