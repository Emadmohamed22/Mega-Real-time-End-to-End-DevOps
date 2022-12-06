pipeline{
    
    agent any 
    tools {
        maven "3.8.6"
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
        stage('upload war file to nexus'){
            steps{
                script{
                    nexusArtifactUploader artifacts: [[artifactId: 'springboot', classifier: '', file: 'target/Uber.jar', type: 'jar']], credentialsId: 'nexus-auth', groupId: 'org.springframework.boot', nexusUrl: '127.0.0.1:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'Mega-Release', version: '2.0.0'
                }
            }
        }
    }
}
