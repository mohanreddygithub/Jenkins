node {
    stage('Checkout Source Code'){
                git 'https://github.com/mohanreddygithub/Jenkins'
        }
    stage ('Build JenkinsAssignment and 1.0-SNAPSHOT'){
        def mvnHome = tool name: 'maven3', type: 'maven'
        sh "${mvnHome}/bin/mvn package"
        }
    stage ('Deploying JenkinsAssignment and 1.0-SNAPSHOT'){
        //sh "scp -i awsdevops.pem /var/lib/jenkins/workspace/jenkins-git-and-maven/target/JenkinsAssignment.war ec2-user@3.6.93.109:/opt/tomcat8/webapps/"
   // sh "scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/jenkins-git-and-maven/target/JenkinsAssignment.war ec2-user@${tomcatDevIp}:${webApps}myweb.war"   
    sh "scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/jenkins-git-and-maven/target/JenkinsAssignment.war ec2-user@$3.6.93.109:$/opt/tomcat8/webapps/"   
    }
    stage ('Executing tests'){
       'http://3.6.93.109:8080/JenkinsAssignment/'
      }
}
