pipeline{
  agent any
  environment{
    webimage="localhost:5000/webinterface"
    apiimage='imageapi'
    dockerregistryurl='localhost:5000'
  }
  stages{
    stage('building docker image'){
      steps{
        script{
          docker.build(webimage,"./frontend/")
        }    
    }
    }
    stage('pushing images to docker registry'){
      steps{
        script{
          dockerImage.push(webimage)
        }
      }
    }
  }
}