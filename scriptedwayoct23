node
{

def mavenHome = tool name: "maven3.9.3"

properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '3', daysToKeepStr: '', numToKeepStr: '3')), pipelineTriggers([pollSCM('* * * * *')])])

stage ("Get the code from GitHub")
{
git branch: 'development', credentialsId: '71e70e97-6e2e-4344-a58e-9fdb07f75cc2', url: 'https://github.com/kaksha2204/maven-web-application.git'
}

stage ("Build the package in Maven")
{
sh "${mavenHome}/bin/mvn clean package"
}
/*
stage ("Generate SonarQube Report")
{
sh "${mavenHome}/bin/mvn sonar:sonar"
}

stage ("Upload the artifact into Nexus")
{
sh "${mavenHome}/bin/mvn deploy"
}

stage ("Deploy the app into Tomcat")
{
sshagent(['ac41d27e-918e-4e14-a5b2-31cfa1431746']) {
sh 'scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@3.110.41.228:/opt/apache-tomcat-9.0.80/webapps'
}
}

stage ("Send email notification")
{
emailext body: '''Build Over....

Thanks
Kaksha''', subject: 'Build Over....', to: 'panchalkaksha@gmail.com'
}
*/
}
