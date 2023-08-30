pipeline{
  agent any
  stages{
    stage('SCM Checkout'){
      steps{
        git 'https://github.com/sankar0812/nodeapp_demo.git'
      }
    }
    stage('Build docker image'){
      steps{
        sh 'docker build -t nodeapp .'
      }
    }
    stage('nexus repo'){
      steps{
       
      }
    }
    stage('Run container'){
      steps{
        sh 'docker run -d --name nodeapp -p 3000:3000 nodeapp'
      }
    }
  }
}
