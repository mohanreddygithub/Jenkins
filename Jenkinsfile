node {
    stage('Checkout Source Code'){
                git 'https://github.com/mohanreddygithub/Jenkins'
        }
    stage ('Build JenkinsAssignment and 1.0-SNAPSHOT'){
        def mvnHome = tool name: 'maven3', type: 'maven'
        sh "${mvnHome}/bin/mvn package"
        }
}
