pipeline {
	
    agent any
    stages {
        
        stage('build war-file'){
	        steps {
	        	sh '/usr/bin/apache-maven-3/bin/mvn clean'
	        	sh '/usr/bin/apache-maven-3/bin/mvn install'
	        }
	    }
	    
	    stage('deploy war-file to tomcat'){
	        steps {
	            sh "curl -v -u war-deployer:Welcome1! -T ./target/jenkins-java-example.war 'http://localhost:8080/manager/text/deploy?path=/jenkins-java-example&update=true'"
	        }
	    }
    }
}