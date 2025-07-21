//jqglqngl
pipeline {
agent {
label {
		label "built-in"
		customWorkspace "/mnt/rahul"
		
		}
		}
		
	stages {
		
		stage ('CLEAN_OLD_M2') {
			
			steps {
				sh " rm -rf * "
				
				
			}
			
		}
	
		stage ('MAVEN_BUILD') {
		
			steps {
						
						sh "mvn clean install"
			
			}
			
		
		}
		
		stage ('COPY_WAR_TO_Server'){
		
				steps {
						
						sh '''
					cp -r /mnt/rahul/project/target/LoginWebApp.war /mnt/servers/apache-tomcat-10.1.43/webapps/
                                        cd /mnt/servers/apache-tomcat-10.1.43/bin/
					./shutdown.sh
                                        ./startup.sh
					'''

						}
				
				}
	
	
	
	}
		
}
