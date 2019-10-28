pipeline {
  agent { docker { image 'python:3.7.2' } }
  stages {    
    stage('build') {
      steps {
        script {
          System.setProperty("Dorg.jenkinsci.plugins.durabletask.BourneShellScript.LAUNCH_DIAGNOSTICS", "True")
      }
        sh 'pip install -r requirements.txt'
      }
    }
    stage('test') {
      steps {
        sh 'python -m tests.test_hello'
      }
      post {
        always {
          junit 'test-reports/*.xml'
        }
      }
    }
  }
}