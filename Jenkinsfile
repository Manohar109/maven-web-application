node
{
	def MavenHome= tool name:"maven_3.8.4"
	properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'JobLocalConfiguration', changeReasonComment: '']])
	
stage('CheckoutCode')
	{
	git branch: 'development', credentialsId: '3767a0fd-b33a-4360-8a65-02c10a319b41', 
	url: 'https://github.com/Manohar109/maven-web-application.git'
	}

stage('Build')
	{
	sh "${MavenHome}/bin/mvn clean package"  
	}
/*	
stage('ExecuteSonarQubeReport')
	{
	sh "${MavenHome}/bin/mvn sonar:sonar"
	}

stage ('Upload Artifacts in to the Nexus')
	{
	sh "${MavenHome}/bin/mvn deploy"
	}
	
stage ('Deploy Application into Tomcat Server')
	{
	sshagent(['b2943cb5-225b-4ee9-a3c0-aaaeaa850a30']) {
    
	sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@3.110.191.188:/opt/apache-tomcat-9.0.55/webapps"
}
	}
stage ('Send email Notification'){
emailext body: '''Build Over

Regards,
Manohar K
''', subject: 'Build Over', to: 'manukumar.cv@gmail.com'
}
*/
}
