node {
    stage('Checkout Source Code'){
                git 'https://github.com/mohanreddygithub/Jenkins'
        }
    stage ('Build app and 1.1'){
        def mvnHome = tool name: 'maven3', type: 'maven'
        sh "${mvnHome}/bin/mvn package"
        }
}
