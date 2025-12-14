pipeline {
  agent any 
    stages {
      stage ('git checkout') {
        steps {
               checkout scm
            }
      }  
      stage ('install dependencies') {
        steps {
                sh 'python3 -m venv venv'
                sh 'venv/bin/pip install -r requirements.txt'
            }
      }
      stage ('test') {
        steps {
                sh "PYTHONPATH=\\$PWD 'venv/bin/pytest"
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


    
