pipeline{
  agent any
  tools{
    maven 'maven'
  }
  stages{
    stage("Checkout"){
      steps{
        git branch : "main",
          url: "https://github.com/anjanm0545-dotcom/immute.git"
      }
    }
    stage("Build"){
      steps{
        sh 'mvn compile'
      }
    }
    stage("Test"){
      steps{
        sh 'mvn test'
      }
    }
    stage("Run Aplication"){
      steps{
          sh 'mvn exec:java -Dexec.mainClass=com.example.App'
      }
    }
  }
  post{
    success{
      echo 'Build and Deploy Successfull'
    }
    failure{
      echo 'Build failure'
    }
  }
}

      
