pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'pip install -r requirements.txt'
      }
    }
    stage('test') {
      steps {
        sh 'python test.py'
        sh 'pip install Flask --upgrade'
      }
      post {
        always {
          junit 'test-reports/*.xml'
        }
      }    
    }
  }
}
