pipeline    {
  agent any

  stages {
    stage('Git Checkout') {
      steps {
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs:[[url: 'https://github.com/gowthamjul23/test-repo.git']]])
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
    stage('Post Deploy Tetjob1'){
      steps{
          build(job: "Testjob1")
      }           
    }
    stage('Post Deploy Tetjob2'){
      steps{
          build(job: "Testjob2")
      }           
    }
  }
}
