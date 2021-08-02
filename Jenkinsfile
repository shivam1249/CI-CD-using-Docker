pipeline {
    agent any
	
	 
 stages {
      stage('checkout') {
           steps {
             
                git branch: 'master', url: 'https://github.com/shivam1249/CI-CD-using-Docker.git'
             
          }
        }
	 stage('Execute Maven') {
           steps {
             
                sh 'mvn package'             
          }
        }
        

  stage('Docker Build and Tag') {
           steps {
              
                sh 'docker build -t jenkins_play12:latest .' 
                sh 'docker tag jenkins_play12 1204199507/jenkins_play12:latest'
                //sh 'docker tag jenkins_play12 1204199507/jenkins_play12:$BUILD_NUMBER'
               
          }
        }
     

     
      stage('Run Docker container on Jenkins Agent') {
             
            steps 
			{
                sh "docker run -d -p 8080:8080 1204199507/jenkins_play12"
 
            }
        }
 
     }
	}    
