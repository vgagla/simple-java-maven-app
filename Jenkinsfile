def gv

pipeline {
  agent any
  parameters{
    choice(name: 'VERSION', choices: ['1.1','1.2','1.3'], description: "Version Choices")
    booleanParam(name: 'executeTests', defaultValue: true, description: 'Check for Tests'  )
  }  
  stages{
    stage("Init") {
       steps{
          script {
            gv = load 'script.groovy'
          }
       }
    }
    stage("Build") {
        steps{
          script {
            gv.appBuild()
          }
       }
    }
    stage("Test") {
      when{
        expression{
          params.executeTests
        }
      }
      steps{
        echo "Deploying the version : ${params.VERSION}"
      }
    }
    stage("Deploy") {
      steps{
        echo "Deploying the version : ${params.VERSION}"
      }
    }
  }
}
