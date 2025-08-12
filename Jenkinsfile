pipeline {
   agent any
   stages {
         stage('1') {
             steps {
                  
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
