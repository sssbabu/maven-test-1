pipeline {
 agent none
 stages{
  stage("build and SonarQube Analysis")
  {
   agent any
    steps {
	 withSonarQubeEnv('sonar_server')
	 {
	  sh "mvn clean package sonar -Dsonar.projectKey=jenkins-project1 -Dsonar.projectName='jenkins-project1'"
	 }
	}
  }
 }
}
