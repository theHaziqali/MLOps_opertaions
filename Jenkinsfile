pipeline{
  agent any
  
  
  stages{
    
    stage('checkout'){
      steps{
      checkout scm
      }
    }

    
     stage('Build') {
      steps {
        script {
          sh 'echo bingo!'
          sh 'docker build -t python:0.0.1 .'
          sh'sudo docker login'
         ' username: Haziqali'
         ' password : 12602700h'
          echo 'tagging docker image'
          sh 'docker tag python:0.0.1 haziq/python:0.0.1

          sh 'docker push haziq/python:0.0.1'

        }
      
  }

     }
             stage('Execute') {
        steps {
            sh 'sudo kubectl version'
            sh 'sudo kubectl apply -f deployment.yaml'
            sh 'sudo kubectl apply -f service.yaml'
        }
  }
}
}
