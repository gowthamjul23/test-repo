pipeline    {
  agent any

  stages {
    stage('Git Checkout') {
      steps {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs:[[url: 'https://github.com/LuisJoseSanchez/hello-world-java.git']]])
      }
    }
    stage('Java compile') {
      steps  {
        script {
          sh '''
            javac HelloWorld.java
            java HelloWorld
          '''
        }
      }
    }
    stage('Deploy Tetjob1'){
      steps{
          build(job: "Testjob1")
      }           
    }
    stage('Deploy Tetjob2'){
      steps{
          build(job: "Testjob2")
      }           
    }
  }
}
