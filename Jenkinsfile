pipeline { 
     agent any
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
