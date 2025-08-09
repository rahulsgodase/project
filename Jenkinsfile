pipeline {
        agent {
		        label { 
				        label 'built-in'
						customWorkspace '/mnt/w-space'
						}
				}
                  stages {
  				           stage ('stage-1') {
						     steps { 
							      sh '''
								     mvn clean install
									 '''
									 }
									}
						   stage ('stage-2-install docker') {
						      steps {
						            sh '''
									yum install docker -y
									systemctl start docker
									'''
									}
								}
								
							stage('stage-3 install docker-compose') {
							    steps {
								    sh '''
			                         rm - rf /usr/local/bin/docker-compose
									 curl -SL https://github.com/docker/compose/releases/download/v2.39.1/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose
									 chmod +x /usr/local/bin/docker-compose
									 sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
									 '''
									 }
								}

							stage('stage-3') {
							   steps {
							   sh '''
							      cp /mnt/docker-compose.yaml /mnt/w-space
								  cd /mnt/w-space
								  docker-compose down || true
								  docker-compose up 
								  '''
								  }
								 }
						}
						
					}
                   			
