node {
    stage('Checkout Source Code'){
                git 'https://github.com/mohanreddygithub/Jenkins'
        }
    stage ('Build JenkinsAssignment and 1.0-SNAPSHOT'){
        def mvnHome = tool name: 'maven3', type: 'maven'
        sh "${mvnHome}/bin/mvn package"
        }
    stage ('Deploying JenkinsAssignment and 1.0-SNAPSHOT'){
        cd /var/lib/jenkins/workspace/jenkins-git-and-maven/target
        scp -i ~/awsdevops.pem JenkinsAssignment.war ec2-user@3.6.93.109:/opt/tomcat8/webapps/
    }
}
