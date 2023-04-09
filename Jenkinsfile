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
            bat 'docker stop mlops'
          } catch(err) {
            bat 'echo Container mlops Already Stopped'
          }
          try {
              bat 'docker rm mlops'
          } catch(err1) {
            bat 'echo done'
          }
          try {
            bat 'docker image rm mlops'
          } catch (err) {
            bat 'echo Image mlops Already Removed'
          }
          bat 'echo bingo!'
          bat 'docker build -t app.py .'
          echo 'Running docker image'
          bat 'docker run app.py

        }
  }
}
