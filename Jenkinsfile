//declarative programming using predefined keywords

echo 'Stating the test'

pipeline
{
 agent any
 //{
  //label ''
 //}
 
 stages
 {
   stage('build')
   {
     steps 
     {
     	sh 'make'    
     	echo "Branhc name is ${BRANCH_NAME}" 	
     }     
   }
   
   stage('test')
   {
    when{
        
        expression{
            
            BRANCH_NAME = 'dev'
        }


    }

 //Steps will be eecuted only when the expression is true   
     steps 
     {
     	sh 'make check' 
     	junit 'report/**/*.xml'
     	testNg 'reports'  
     	/** Junit & testNg plugins provide the commands */    	
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