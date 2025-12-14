pipeline {
  agent any {
    stages {
      stage ('git checkout') {
        steps {
               checkout scm
            }
        }  
      stage ('install dependecies') {
        steps {
                sh 'python3 -m venv venv'
                sh 'venv/bin/pip install -r requirements.txt'
            }
        }
      stage ('test') {
        steps {
                sh 'venv/bin/pytest'
            }
        }
    }
    post {
      success {
        echo 'build succcess'
      }
      failure {
            echo 'Build or tests failed.'
        }
    }
 }
}

    
