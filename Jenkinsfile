pipeline { 
     agent any 
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
} 
