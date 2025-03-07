pipeline{
 tools{
        jdk 'JAVA_HOME'
        maven 'M2_HOME'
    }
     agent any
	  
	  stages{
	  
	  stage("checkout"){
	   steps{
	   git 'https://github.com/sssbabu/maven-test-1.git'
	   }
	                  }
	
	   stage("compile"){
	    steps{
		 sh 'mvn compile'
		}
		}
       stage("test"){
	    steps{
		 sh 'mvn test'
		}
		}
	
       stage("package"){
	    steps{
		 sh 'mvn clean package'
                 sh "mv target/*.jar target/myweb.jar"

		}
		}
stage(backup)
		  {
  steps{

	nexusArtifactUploader artifacts: [[artifactId: 'app', classifier: '', file: 'target/myweb.jar', type: 'jar']], credentialsId: 'nexus1', groupId: 'com.idream', nexusUrl: '52.66.235.112:8081/repository/maven-releases/', nexusVersion: 'nexus2', protocol: 'http', repository: 'maven-releases', version: '1.0'
	  
  }
	
}
	}
