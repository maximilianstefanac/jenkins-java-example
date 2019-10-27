pipeline {
    agent any
    stages {
        stage('build war-file'){
	        steps {
	            sh '/usr/bin/apache-maven-3/bin/mvn war:war'
	        }
	    }
	    
	    stage('deploy war-file to tomcat'){
	        steps {
	            sh '/usr/bin/apache-maven-3/bin/mvn tomcat7:deploy'
	        }
	    }
    }
}