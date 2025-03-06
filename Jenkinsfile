pipeline {
 agent none
 stages{
  stage("build and SonarQube Analysis")
  {
   agent any
    steps {
	 withSonarQubeEnv('sonarqubeproject')
	 {
	  sh "mvn clean package sonar:sonar -Dsonar.projectKey=sonarqubeproject -Dsonar.projectName='sonarqubeproject'"
	 }
	}
  }
 }
}
