pipeline {
    agent any
    stages {
        stage('build war-file'){
	        steps {
	            sh '/usr/bin/apache-maven-3/bin/mvn war:war'
	        }
	    }
    }
}