# Author : DevOps Mohanraj & Balaji

pipeline{
  agent any
  tools {
      git 'git'
      maven 'maven'
}

  environment {
        IMAGE_TAG = "${env.BUILD_NUMBER}"
        
  }

stages{

   stage('SCM Checkout'){
     steps{
 git 'https://github.com/mohansgithub/simple-web-app.git'
     }
   }
                        
   stage('Unit Testing'){
     steps{
             bat label: '', script: 'mvn clean test'
     }
   }
      stage('Maven packing'){
     steps{
           bat label: '', script: 'mvn clean package'
        }
    }
    
   stage('Input') {
            steps {
                input('Do you want to proceed to dev?')
            }            
            
    }

    
}
}
           