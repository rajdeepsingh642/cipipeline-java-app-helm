
pipeline{
    
    agent any 
    
    stages {
        
        stage('Git Checkout'){
            
            steps{
                
               git branch: 'main', url: 'https://github.com/rajdeepsingh642/cipipeline-java-app-helm.git'
                    
                    
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
                   
               stage('Quality Gate Status'){
                
                steps{
                    
                    script{
                        waitForQualityGate abortPipeline: false, credentialsId: 'sonar-qube'       
                   
                        
                    }     
        }          
                       
        }
                    
                
    }
}  
}
