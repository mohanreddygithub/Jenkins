pipeline {
   agent any
    stages{
stage('SCM Checkout'){
      steps {
          git branch: 'master',  
         url: 'https://github.com/mohanreddygithub/Jenkins'
        }
    }
    stage('Mvn Package'){
    steps {  
  script {
       def mvnHome = tool name: 'maven3', type: 'maven'
        sh "${mvnHome}/bin/mvn package"
  }
        }
    }
    
       stage('Deploying JenkinsAssignment and 1.0-SNAPSHOT'){
steps {
       script {
  def tomcatDevIp = '3.6.93.109'
  def tomcatHome = '/opt/tomcat8/'
  def webApps = tomcatHome+'webapps/'
  def tomcatStart = "${tomcatHome}bin/startup.sh"
  def tomcatStop = "${tomcatHome}bin/shutdown.sh"
 
  sshagent(['tomcat']) {
                sh "scp -o StrictHostKeyChecking=no target/myweb*.war ec2-user@${tomcatDevIp}:${webApps}myweb.war"
                sh "ssh ec2-user@${tomcatDevIp} ${tomcatStop}"
                sh "ssh ec2-user@${tomcatDevIp} ${tomcatStart}"
            }
       }
}
   }
       
     
       
    }
}

/*
def mvnHome = tool name: 'maven3', type: 'maven'
        sh "${mvnHome}/bin/mvn package"

/*pipeline{
agent any
    stages{
    stage('Checkout Source Code')
        steps{
            git branch: 'master',
                url:'https://github.com/mohanreddygithub/Jenkins'
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
