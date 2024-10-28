pipeline { 
     agent any 
     stages { 
          stage("Compile") { 
               steps { 
                    sh "./compile.sh" 
               } 
          } 
          stage("Unit test") { 
               steps { 
                    sh "./test.sh" 
               } 
          } 
     } 
} 
