node{

def mavenHome= tool name: 'maven3.8.5'

echo "the job name is: ${env.JOB_NAME}"
echo "the build number is: ${env.BUILD_NUMBER}"
echo "the node name is : ${env.NODE_NAME}"

//checkout code state
stage('checkout code'){
git branch: 'development', credentialsId: 'b6da0283-cdaa-4cf5-9337-17ec6e15e2eb', url: 'https://github.com/saibank-apps/maven-web-application.git'
}

//build
stage('build'){
sh "${mavenHome}/bin/mvn clean package"
}

  /*
//ExecutesonarQube report
stage('ExecutesonarQubereport'){
sh "${mavenHome}/bin/mvn sonar:sonar"
}

//uplodeArtifacts into Nexus
stage('uplodeArtifactsintoNexus'){
sh "${mavenHome}/bin/mvn deploy"
}

//Deploy App into Tomcat
stage('deploytotomcat'){
sshagent(['a7b0b7c3-40ba-4c10-8e36-7408d428ad44']) {
sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@172.31.38.144:/opt/apache-tomcat-9.0.68/webapps/"
}
}
 
 */
}//node closing
