pipeline{
  agent any
  environment{
    webimage='webinterface'
    apiimage='imageapi'
  }
  stages{
    stage('building docker image'){
      steps{
        script{
          docker.build(env.webimage,"-f ./frontend/")
        }
        script{
          docker.build(env.apiimage,"-f ./api/")
        }
      }
    }
  }
}