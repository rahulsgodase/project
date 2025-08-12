pipeline {
          agent {
		     label {
		            label 'built-in'
                    customWorkspace '/mnt/ws'					
				}
			}
      stages {
           stage('sg-1') {
                 steps {
				          sh '''
						  mvn clean install
						  '''
					}
		}
		   stage('sg-2') {
		              steps {
					  sh '''
					         cd /root
							 chmod -R 700 update.sh
							 ./update.sh 
							 
                  	cp /mnt/ws/target/LoginWebApp /mnt/servers/apache-tomcat-10.1.44/webapps
							 cd /mnt/servers/apache-tomcat-10.1.44/bin
							 ./shutdown.sh
							 ./startup.sh
						'''
					}
             }
         }
   }		 
	 
				
