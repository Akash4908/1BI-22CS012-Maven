pipeline {
    agent any  
    
  
    tools {
        maven 'Maven'  
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Akash4908/1BI22CS012-Maven.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

     	stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
     	stage('Run Application') {
            steps {
               sh 'java -jar target/MyMavenApp-1.0-SNAPSHOT.jar'
            }
        }            
    }
    post{
    	success{
    		echo 'Build and Deployment Successful'
    	}
    	failure{
    		echo 'Build Failed'	
   	}
   }
}
