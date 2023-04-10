pipeline{
  agent any
  
  
  stages{
    
    stage('checkout'){
      steps{
      checkout scm
      }
    }
    
     stage('Run') {
      steps {
        script {
          try {
            sh 'docker stop mlops'
          } catch(err) {
            sh 'echo Container mlops Already Stopped'
          }
          try {
              sh 'docker rm mlops'
          } catch(err1) {
            sh 'echo done'
          }
          try {
            sh 'docker image rm mlops'
          } catch (err) {
            sh 'echo Image mlops Already Removed'
          }
          sh 'echo bingo!'
          sh 'docker build -t python:0.0.1 .'
          echo 'Running docker image'
          sh 'docker run python:0.0.1'
          sh 'sudo docker tag python:0.0.1 haziq/python:0.0.1'
          sh 'sudo docker push haziq/python:0.0.1'

        }
  }
     }
  }
}
