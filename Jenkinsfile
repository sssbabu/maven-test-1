pipeline {
tools {
	jdk 'JAVA_HOME'
        maven 'M2_HOME'  // Adjust Maven version if needed
    }
 agent none
 
  stage("build and SonarQube Analysis")
  {
   agent any
    steps {
	 withSonarQubeEnv('testsonarq')
	 {
	  // #sh 'mvn clean package sonar:sonar'
          sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=jenkins-project1 -Dsonar.projectName='jenkins-project1'"
	 }
	}
  }
 }
}
