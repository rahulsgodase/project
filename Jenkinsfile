//jqglqngl
pipeline {
agent {
label {
		label "built-in"
		customWorkspace "/mnt/rahul"
		
		}
		}
		
	stages {
		
		
		stage ('MAVEN_BUILD') {
		
			steps {
						
						sh "mvn clean install"
			
			}
			
		
		}
		
		stage ('COPY_WAR_TO_Server'){
		
				steps {
						
						sh '''
                                         chmod -R 777 /mnt/
					cp -r /mnt/rahul/project/target/LoginWebApp.war /mnt/servers/apache-tomcat-10.1.43/webapps/
                                        cd /mnt/servers/apache-tomcat-10.1.43/bin/
					./shutdown.sh
                                        ./startup.sh
					'''

						}
				
				}
	
	
	
	}
		
}
