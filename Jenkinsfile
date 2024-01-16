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
          docker.build(env.webimage,"./frontend/")
          docker.image(env.webimage).tag(env.dockerregistryurl/env.webimage)
        }
    }
    }
    stage('pushing images to docker registry'){
      steps{
        script{
          docker.image("env.dockerregistryurl/env.webimage").push()
        }
      }
    }
  }
}