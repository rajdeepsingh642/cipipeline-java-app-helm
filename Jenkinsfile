pipeline{
    
    agent any 
    
    stages {
        
        stage('Git Checkout'){
            
            steps{
                
                script{
                    
                    git branch: 'main', url: 'https://github.com/vikash-kumar01/mrdevops_javaapplication.git'
                }
            }
        }
        
       
        
        stage('Static code analysis'){
            
            steps{
                
                script{
                    
                   
                        
                        sh 'mvn clean package sonar:sonar'
                    }
                   }
                    
                }
            }
           
            }
        
        
