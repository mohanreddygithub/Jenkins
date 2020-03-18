pipeline {
   agent any
    stages{
stage('Checkout source code'){
      steps {
          git branch: 'master',  
         url: 'https://github.com/mohanreddygithub/Jenkins'
        }
    }
    stage('Build JenkinsAssignment and 1.0-SNAPSHOT'){
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
     sh "scp -i /var/lib/jenkins/workspace/jenkins-git-and-maven/target/awsdevops.pem -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/jenkins-git-and-maven/target/JenkinsAssignment.war ec2-user@${tomcatDevIp}:${webApps}"
        // sh "scp -i awsdevops.pem /var/lib/jenkins/workspace/jenkins-git-and-maven/target/JenkinsAssignment.war ec2-user@3.6.93.109:/opt/tomcat8/webapps"  
     //sh "ssh ec2-user@${tomcatDevIp} ${tomcatStop}"
       //         sh "ssh ec2-user@${tomcatDevIp} ${tomcatStart}"
            }
       }
}
   }
       
          stage ('Executing tests'){
             steps{
                echo "http://3.6.93.109:8080/JenkinsAssignment/"
             
          }
              } 
     
       
    }
}

