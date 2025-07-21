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
						
						sh '''
                                                rm -rf /root/.m2/repository
                                                     mvn clean install
						     
			
			}
			
		
		}
		
		stage ('COPY_WAR_TO_Server'){
		
				steps {
						
						sh '''
                                         chmod -R 777 /mnt/
					 rm -rf /mnt/servers/apache-tomcat-10.1.43/webapps/LoginWebApp.war
                                         rm -rf /mnt/servers/apache-tomcat-10.1.43/webapps/LoginWebApp
					cp -r /mnt/rahul/target/LoginWebApp.war /mnt/servers/apache-tomcat-10.1.43/webapps/
                                        cd /mnt/servers/apache-tomcat-10.1.43/bin/
				
                                        
					'''

						}
				
				}
	
	
	
	}
		
}
