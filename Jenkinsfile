pipeline{
    
    agent any 
    
    stages {
        
        stage('Git Checkout'){
            
            steps{
                
               git branch: 'main', url: 'https://github.com/rajdeepsingh642/cipipeline-java-app-helm.git'
                    
                    
                }
            }
        
        
       
        
        stage('Static code analysis'){
            
            steps{
                
                withSonarQubeEnv(credentialsId: 'sonar-qube') {
                   sh 'mvn clean package sonar:sonar'
                    }
              }
                    
                   
                        
                       
        }
                    
                
    }
}  
           
            
        
        
