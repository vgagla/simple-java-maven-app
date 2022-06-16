pipeline {
  agent any
  tools{
    gradle Gradle-7.4.2
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
  }
}
