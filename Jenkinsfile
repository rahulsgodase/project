pipeline {
   agent {
        label {
                  label 'built-in' 
                  customWorkspace '/mnt/ws'
        }
   }
   stages {
         stage('1') {
             steps {
                  dir ("/mnt/ws/1")
                 sh ' echo " hii all " >> index.html '
             }
         }
          stage('2') {
            steps {
               sh " mvn clean install "
              sh " cp -r target/LoginWebApp /mnt"
          }
   }
}
}
