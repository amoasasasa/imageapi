pipeline{
  agent any
  environment{
    webimage='webinterface'
    apiimage='imageapi'
    dockerregistryurl='localhost:5000'
  }
  stages{
    stage('building docker image'){
      steps{
        script{
          docker.build(webimage,"./frontend/")
          docker.image(webimage).tag(dockerregistryurl/webimage)
        }
    }
    }
    stage('pushing images to docker registry'){
      steps{
        script{
          docker.image("${dockerregistryurl}/${webimage}").push()
        }
      }
    }
  }
}