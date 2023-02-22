pipeline{
    
    agent any 
    
    stages {
        
        stage('Git Checkout'){
            
            steps{
                
               git branch: 'main', url: 'https://github.com/rajdeepsingh642/cipipeline-java-app-helm.git'
                    
                    
                }
        }
        
          stage('UNIT testing'){
            
            steps{
                
                script{
                    
                    sh 'mvn test'
                }
            }
        }
       
        
        stage('Sonar Quality check'){
         agent {
                docker { 
                   image  'maven'
            }
            }
            steps{
                script{
                
                withSonarQubeEnv(credentialsId: 'sonar-qube') {
                   sh "mvn clean install sonar:sonar"
                    }
              }
            }
                   
                        
                       
        }
                    
                
    }
}  
           
            
        
        
