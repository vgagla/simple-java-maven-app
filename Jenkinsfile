pipeline {
  agent any
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
        withGradle(){
          sh './gradlew -v'
        }
      }
    }
  }
}
