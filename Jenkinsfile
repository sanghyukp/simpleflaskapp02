pipeline {
  agent { docker { image 'python' } }
  stages {
    stage('build') {
      steps {
        sh 'pip install -r requirements.txt'
      }
    }
    stage('test') {
      steps {
        sh 'python -m unittest discover'
      }
    }
  }
}