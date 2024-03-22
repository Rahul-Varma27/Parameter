pipeline {
	agent any
	
	parameters {
		choice(name: 'ENVIRONMENT', choices: ['QA','UAT'], description: 'Pick Environment value')
	}
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/rahul/Documents/Extractfile/apache-maven-3.9.6/bin/mvn install'
	                 }}
		stage('Deployment'){
		    steps {
			script {
			 if ( env.ENVIRONMENT == 'QA' ){
        	sh 'cp target/Parameter.war /home/rahul/Documents/Extractfile/apache-tomcat-9.0.85/webapps'
        	echo "deployment has been done on QA!"
			 }
	                 else if ( env.ENVIRONMENT == 'UAT' ){
    		sh 'cp target/Parameter.war /home/rahul/Documents/Extractfile/apache-tomcat-9.0.85/webapps'
    		echo "deployment has been done on UAT!"
			}
			echo "deployment has been done!"
			
			
			}}}	
}}
