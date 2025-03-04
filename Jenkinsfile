pipeline {
tools {
	jdk 'JAVA_HOME'
        maven 'M2_HOME'  // Adjust Maven version if needed
    }
 agent none
 stages{
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
