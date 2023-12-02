//declarative programming using predefined keywords

echo 'Stating the test'

pipeline
{
 agent any
 
 stages
 {
   stage('build')
   {
     steps 
     {
     	echo 'Branch name is'+ env.BRANCH_NAME
     }     
   }
   
   stage('test')
   {
    when{
        
        expression{
            
            env.BRANCH_NAME = 'dev'
        }


    }

 //Steps will be eecuted only when the expression is true   
     steps 
     {
     	echo 'test phase for master branch'  	
     }     
   }
   
   stage('deploy')
   {
     steps 
     {
     	sh 'make publish'
     }     
   }  
   
 }

}