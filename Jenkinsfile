pipeline {
  agent any
  parameters{
    choice(name: 'VERSION', choices: ['1.1','1.2','1.3'], description: "Version Choices")
    booleanParam(name: 'executeTests', defaultValue: true, description: 'Check for Tests'  )
  }
  tools{
    gradle 'Gradle-7.4.2'
  }
  stages{
    stage("build front end") {
      steps{
        echo "Executing yarn..."
        nodejs("Node-10.17"){
          sh 'yarn install'
        }
      }
    }
    stage("build backend") {
      steps{
        echo "building the backend..."
        sh './gradlew --version'
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
