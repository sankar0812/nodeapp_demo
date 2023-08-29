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
        nexusArtifactUploader artifacts: [[artifactId: 'node-project', classifier: '', file: 'v2/node', type: 'js']], credentialsId: 'nexus_credentilas', groupId: 'node-project', nexusUrl: '192.168.29.106:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'docker_repo', version: '1.0'
      }
    }
    stage('Run container'){
      steps{
        sh 'docker run -d --name nodeapp -p 3000:3000 nodeapp'
      }
    }
  }
}
