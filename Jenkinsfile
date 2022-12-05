pipeline{
    
    agent any 
    tools {
        maven "3.8.6"
        SonarQubeScanner "4.7.0.2747"

    }
    stages {
        
        stage('Git Checkout'){
            
            steps{
                
                script{
                    
                    git branch: 'main', url: 'https://github.com/Emadmohamed22/Mega-Real-time-End-to-End-DevOps.git'
                }
            }
        }
        stage('UNIT testing'){
            
            steps{
                
                script{
                    
                    sh 'mvn test'
                }
            }
        }
        stage('Integration testing'){
            
            steps{
                
                script{
                    
                    sh 'mvn verify -DskipUnitTests'
                }
            }
        }
        stage('Maven build'){
            
            steps{
                
                script{
                    
                    sh 'mvn clean install'
                }
            }
        }
        stage('Static code analysis'){
            steps{
                    withSonarQubeEnv(installationName: 'sonarserver',credentialsId: 'sonar-api'){
                    sh 'mvn clean verify sonar:sonar'
                }
            }
        }
    }
}
