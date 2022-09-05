 pipeline {
  
  agent any
 
  stages {
  
  stage('Pull image to Docker Hub') {
          
        steps 
        {
            sh  'docker pull ashwinimesh/node:latest'
          
        }
       }
      
     
   stage('Run Docker container on Jenkins Agent') {
             
         steps 
         {
             sh "docker run -d -p 3019:3000 ashwinimesh/node:latest"
 
          }
        }
 stage('Run Docker container on remote hosts') {
             
            steps {
                sh 'ssh -v -o StrictHostKeyChecking=no  root@172.31.34.89 docker run -d -p 3019:3000 ashwinimesh/node:latest'
 
            }
        }
    }
 }
