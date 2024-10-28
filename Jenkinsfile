pipeline { 
     agent any
     triggers {
        pollSCM('H/5 * * * *')
     }
     options {
          disableConcurrentBuilds()
          retry(3)
          timeout(time: 4, unit: 'MINUTES')
          timestamps()
     } 
     environment { 
          MY_ENV_VAR = 'yomama'
     }
     stages { 
          stage("Compile") {
               when {
                    branch 'main'
                    buildingTag()
               }
               steps { 
                    sh "/bin/bash compile.sh" 
               } 
          } 
          stage("Unit test") {
               when {
                    branch 'main'
                    buildingTag()
               }
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
