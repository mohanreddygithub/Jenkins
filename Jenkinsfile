pipeline{
agent any
    stages{
    stage('Checkout Source Code')
        steps{
            git branch: 'master',
                url": 'https://github.com/mohanreddygithub/Jenkins'
            
        }
    }
}




/*pipeline {
    agent any
      stages{
         stage('Checkout Source Code') 
                steps{
                    git branch: 'master',  
                    url: 'https://github.com/mohanreddygithub/Jenkins'            
                    }
               }
        stages{
            stage('Build JenkinsAssignment and 1.0-SNAPSHOT')
                steps{
                    def mvnHome = tool name: 'maven3', type: 'maven'
                    sh "${mvnHome}/bin/mvn package"
                    }
                 }
    
            }
*/
