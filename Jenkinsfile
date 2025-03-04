pipeline {
tools {
	jdk 'JAVA_HOME'
        maven 'M2_HOME'  // Adjust Maven version if needed
    }
 agent none
 stages{
   stage('SonarQube Analysis') {
    def mvn = tool 'Default Maven';
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=jenkins-project1 -Dsonar.projectName='jenkins-project1'"
    }
  }
  stage("build and SonarQube Analysis")
  {
   agent any
    steps {
	 withSonarQubeEnv('testsonarq')
	 {
	  sh 'mvn clean package sonar:sonar'
	 }
	}
  }
 }
}
