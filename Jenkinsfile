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
	    	environment {
	    	    TOMCAT_USERNAME = credentials('tomcat-username')
	    	    TOMCAT_PASSWORD = credentials('tomcat-password')
	    	}
	        steps {
	            sh "curl -v -u ${TOMCAT_USERNAME}:${TOMCAT_PASSWORD} -T ./target/jenkins-java-example.war 'http://localhost:8080/manager/text/deploy?path=/jenkins-java-example&update=true'"
	        }
	    }
    }
}