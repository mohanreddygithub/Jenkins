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
                sh "scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/jenkins-git-and-maven/target/JenkinsAssignment.war ec2-user@${tomcatDevIp}:${webApps}JenkinsAssignment.war"
                sh "ssh ec2-user@${tomcatDevIp} ${tomcatStop}"
                sh "ssh ec2-user@${tomcatDevIp} ${tomcatStart}"
            }
       }
}
   }
       
     
       
    }
}

