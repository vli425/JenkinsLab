pipeline { 
     agent any
     triggers {
        pollSCM('H/10 * * * *')
     }
     options {
          disableConcurrentBuilds()
          retry(3)
          timeout(time: 10, unit: 'MINUTES')
          timestamps()
     } 
     environment { 
          MY_ENV_VAR = 'yomama'
     }
     stages { 
          stage("Compile") { 
               steps { 
                    sh "/bin/bash compile.sh" 
               } 
          } 
          stage("Unit test") { 
               steps { 
                    sh "/bin/bash test.sh" 
               } 
          } 
     } 
     post {
          failure {
               echo "POST // FAILURE catch up task reached"
          }
          success {
               echo "POST // SUCCESS task reached, winding down now"
          }
          always {
               echo "POST // ALWAYS cleanup task reached"
          }
     }
} 
