//declarative programming using predefined keywords

echo 'Stating the test'

pipeline
{
 agent 
 	{
    	label 'linux'    
	}
 
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

 //Steps will be executed only when the expression is true   
     steps 
     {
     	echo 'test phase for master branch'  	
     }     
   }
   
   stage('deploy')
   {
     steps 
     {
     	sh 'printenv'
     }     
   }  
   
 }

}